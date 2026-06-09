# NlpSyncUserCreds

- ea: `0x18000b3b0`
- end: `0x18000b5f9`
- name: `NlpSyncUserCreds`
- size: `585`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000b250`

## callees

- `0x18000b3b0`
- `0x18000b600`
- `0x18000c5d0`
- `0x18000cba0`
- `0x18000cc9c`
- `0x18000cde4`
- `0x18000cf88`
- `0x18002f014`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000b447`
- `ntdll!RtlLengthSid` at `0x18000b447`
- `ntdll!RtlReleaseResource` at `0x18000b489`
- `ntdll!RtlReleaseResource` at `0x18000b52b`
- `ntdll!RtlReleaseResource` at `0x18000b489`
- `ntdll!RtlReleaseResource` at `0x18000b52b`
- `ntdll!RtlAcquireResourceShared` at `0x18000b40d`
- `ntdll!RtlAcquireResourceShared` at `0x18000b40d`

## pseudocode

```c
__int64 __fastcall NlpSyncUserCreds(struct _LUID *a1)
{
  DWORD LowPart; // edx
  LONG *p_HighPart; // rax
  struct _SID *v3; // rsi
  __int64 ActiveLogon; // rax
  __int64 v6; // rdi
  void *v7; // r14
  size_t v8; // r15
  struct _SID *v9; // rax
  _QWORD *v10; // rcx
  unsigned __int8 IsLocalUser; // al
  int v13; // ebp
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING v15; // [rsp+30h] [rbp-48h] BYREF

  LowPart = a1->LowPart;
  p_HighPart = &a1->HighPart;
  v3 = 0;
  v14 = 0;
  v15 = 0;
  if ( LowPart == 997 )
  {
    if ( !*p_HighPart )
      goto LABEL_12;
LABEL_3:
    if ( LowPart != 999 )
      goto LABEL_4;
    goto LABEL_13;
  }
  if ( LowPart != 996 )
    goto LABEL_3;
LABEL_13:
  if ( !*p_HighPart )
    goto LABEL_12;
LABEL_4:
  if ( !(*p_HighPart | LowPart) )
    goto LABEL_12;
  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  ActiveLogon = NlpFindActiveLogon(a1);
  v6 = ActiveLogon;
  if ( !ActiveLogon )
  {
LABEL_11:
    RtlReleaseResource(&NlpActiveLogonLock);
    goto LABEL_12;
  }
  v7 = *(void **)(ActiveLogon + 64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
  v8 = RtlLengthSid(v7);
  v9 = (struct _SID *)((__int64 (__fastcall *)(size_t))LsaFunctions->AllocatePrivateHeap)(v8);
  v3 = v9;
  if ( v9 )
  {
    v13 = 0;
    memcpy_0(v9, v7, v8);
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_11;
    v13 = -1073741670;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
  }
  v10 = WPP_GLOBAL_Control;
LABEL_26:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_(v10[2], 19, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
  if ( v13 < 0
    || (int)NtLmDuplicateUnicodeString(&v14, v6 + 72) < 0
    || (int)NtLmDuplicateUnicodeString(&v15, v6 + 88) < 0 )
  {
    goto LABEL_11;
  }
  RtlReleaseResource(&NlpActiveLogonLock);
  if ( NlpShouldUpdateDpapi(v3, a1) )
  {
    NlpUpdateCredsInMatchingLogons(a1, &v14, &v15);
    IsLocalUser = NlpIsLocalUser(v3);
    NlpResyncDpapiForLogon(a1, IsLocalUser != 0);
  }
LABEL_12:
  ((void (__fastcall *)(struct _SID *))LsaFunctions->FreePrivateHeap)(v3);
  ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v14.Buffer);
  return ((__int64 (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(v15.Buffer);
}

```

## disassembly

```asm
0x18000b3b0  push    rbx
0x18000b3b2  push    rbp
0x18000b3b3  push    rsi
0x18000b3b4  push    rdi
0x18000b3b5  push    r14
0x18000b3b7  push    r15
0x18000b3b9  sub     rsp, 48h
0x18000b3bd  mov     edx, [rcx]
0x18000b3bf  lea     rax, [rcx+4]
0x18000b3c3  xor     esi, esi
0x18000b3c5  xorps   xmm0, xmm0
0x18000b3c8  xorps   xmm1, xmm1
0x18000b3cb  mov     rbx, rcx
0x18000b3ce  movups  xmmword ptr [rsp+78h+var_58.Length], xmm0
0x18000b3d3  movups  xmmword ptr [rsp+78h+var_48.Length], xmm1
0x18000b3d8  cmp     edx, 3E5h
0x18000b3de  jz      loc_18000B4EB
0x18000b3e4  cmp     edx, 3E4h
0x18000b3ea  jz      loc_18000B4E2
0x18000b3f0  cmp     edx, 3E7h
0x18000b3f6  jz      loc_18000B4E2
0x18000b3fc  or      edx, [rax]
0x18000b3fe  jz      loc_18000B48F
0x18000b404  mov     dl, 1; Wait
0x18000b406  lea     rcx, NlpActiveLogonLock; Resource
0x18000b40d  call    cs:__imp_RtlAcquireResourceShared
0x18000b413  mov     rcx, rbx; void *
0x18000b416  call    NlpFindActiveLogon
0x18000b41b  mov     rdi, rax
0x18000b41e  test    rax, rax
0x18000b421  jz      short loc_18000B482
0x18000b423  mov     r14, [rax+40h]
0x18000b427  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b42e  lea     rbp, WPP_GLOBAL_Control
0x18000b435  cmp     rcx, rbp
0x18000b438  jz      short loc_18000B444
0x18000b43a  test    byte ptr [rcx+1Ch], 8
0x18000b43e  jnz     loc_18000B572
0x18000b444  mov     rcx, r14; Sid
0x18000b447  call    cs:__imp_RtlLengthSid
0x18000b44d  mov     r15d, eax
0x18000b450  mov     rax, cs:LsaFunctions
0x18000b457  mov     ecx, r15d
0x18000b45a  mov     rax, [rax+180h]
0x18000b461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b466  mov     rsi, rax
0x18000b469  test    rax, rax
0x18000b46c  jnz     loc_18000B58C
0x18000b472  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b479  cmp     rcx, rbp
0x18000b47c  jnz     loc_18000B59E
0x18000b482  lea     rcx, NlpActiveLogonLock; Resource
0x18000b489  call    cs:__imp_RtlReleaseResource
0x18000b48f  mov     rax, cs:LsaFunctions
0x18000b496  mov     rcx, rsi
0x18000b499  mov     rax, [rax+188h]
0x18000b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a5  mov     rax, cs:LsaFunctions
0x18000b4ac  mov     rcx, [rsp+78h+var_58.Buffer]
0x18000b4b1  mov     rax, [rax+188h]
0x18000b4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4bd  mov     rax, cs:LsaFunctions
0x18000b4c4  mov     rcx, [rsp+78h+var_48.Buffer]
0x18000b4c9  mov     rax, [rax+188h]
0x18000b4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d5  add     rsp, 48h
0x18000b4d9  pop     r15
0x18000b4db  pop     r14
0x18000b4dd  pop     rdi
0x18000b4de  pop     rsi
0x18000b4df  pop     rbp
0x18000b4e0  pop     rbx
0x18000b4e1  retn
0x18000b4e2  cmp     [rax], esi
0x18000b4e4  jz      short loc_18000B48F
0x18000b4e6  jmp     loc_18000B3FC
0x18000b4eb  cmp     [rax], esi
0x18000b4ed  jz      short loc_18000B48F
0x18000b4ef  jmp     loc_18000B3F0
0x18000b4f4  test    ebp, ebp
0x18000b4f6  js      short loc_18000B482
0x18000b4f8  lea     rdx, [rdi+48h]
0x18000b4fc  lea     rcx, [rsp+78h+var_58]
0x18000b501  call    NtLmDuplicateUnicodeString
0x18000b506  test    eax, eax
0x18000b508  js      loc_18000B482
0x18000b50e  lea     rdx, [rdi+58h]
0x18000b512  lea     rcx, [rsp+78h+var_48]
0x18000b517  call    NtLmDuplicateUnicodeString
0x18000b51c  test    eax, eax
0x18000b51e  js      loc_18000B482
0x18000b524  lea     rcx, NlpActiveLogonLock; Resource
0x18000b52b  call    cs:__imp_RtlReleaseResource
0x18000b531  mov     rdx, rbx; struct _LUID *
0x18000b534  mov     rcx, rsi; struct _SID *
0x18000b537  call    ?NlpShouldUpdateDpapi@@YAEPEAXPEBU_LUID@@@Z; NlpShouldUpdateDpapi(void *,_LUID const *)
0x18000b53c  test    al, al
0x18000b53e  jz      loc_18000B48F
0x18000b544  lea     r8, [rsp+78h+var_48]; struct _UNICODE_STRING *
0x18000b549  mov     rcx, rbx; struct _LUID *
0x18000b54c  lea     rdx, [rsp+78h+var_58]; struct _UNICODE_STRING *
0x18000b551  call    ?NlpUpdateCredsInMatchingLogons@@YAJPEAU_LUID@@PEAU_UNICODE_STRING@@1@Z; NlpUpdateCredsInMatchingLogons(_LUID *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18000b556  mov     rcx, rsi; void *
0x18000b559  call    ?NlpIsLocalUser@@YAEPEAX@Z; NlpIsLocalUser(void *)
0x18000b55e  xor     edx, edx
0x18000b560  mov     rcx, rbx
0x18000b563  test    al, al
0x18000b565  setnz   dl
0x18000b568  call    ?NlpResyncDpapiForLogon@@YAXPEAU_LUID@@W4DpapiResyncType@@@Z; NlpResyncDpapiForLogon(_LUID *,DpapiResyncType)
0x18000b56d  jmp     loc_18000B48F
0x18000b572  mov     rcx, [rcx+10h]
0x18000b576  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x18000b57d  mov     edx, 11h
0x18000b582  call    WPP_SF_
0x18000b587  jmp     loc_18000B444
0x18000b58c  xor     ebp, ebp
0x18000b58e  mov     r8, r15; Size
0x18000b591  mov     rdx, r14; Src
0x18000b594  mov     rcx, rsi; void *
0x18000b597  call    memcpy_0
0x18000b59c  jmp     short loc_18000B5BE
0x18000b59e  test    byte ptr [rcx+1Ch], 1
0x18000b5a2  mov     ebp, 0C000009Ah
0x18000b5a7  jz      short loc_18000B5C5
0x18000b5a9  mov     rcx, [rcx+10h]
0x18000b5ad  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x18000b5b4  mov     edx, 12h
0x18000b5b9  call    WPP_SF_
0x18000b5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5c5  lea     rax, WPP_GLOBAL_Control
0x18000b5cc  cmp     rcx, rax
0x18000b5cf  jz      loc_18000B4F4
0x18000b5d5  test    byte ptr [rcx+1Ch], 8
0x18000b5d9  jz      loc_18000B4F4
0x18000b5df  mov     rcx, [rcx+10h]
0x18000b5e3  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x18000b5ea  mov     edx, 13h
0x18000b5ef  call    WPP_SF_
0x18000b5f4  jmp     loc_18000B4F4
```
