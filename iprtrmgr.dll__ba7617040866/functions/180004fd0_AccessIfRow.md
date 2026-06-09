# AccessIfRow

- ea: `0x180004fd0`
- end: `0x18000524a`
- name: `AccessIfRow`
- size: `634`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x180004fd0`
- `0x18000ac60`
- `0x180017bb8`
- `0x18001b8ec`
- `0x18002e558`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800050f3`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800050f3`
- `ntdll!RtlReleaseResource` at `0x1800051c2`
- `ntdll!RtlReleaseResource` at `0x1800051c2`
- `ntdll!RtlAcquireResourceShared` at `0x1800050fb`
- `ntdll!RtlAcquireResourceShared` at `0x1800050fb`

## string_xrefs

- `0x18000504d`: `AccessIfRow`
- `0x1800050b7`: `Leaving: AccessIfRow`
- `0x180005204`: `Leaving: AccessIfRow`
- `0x180005149`: `AccessIfRow: Wrong query type %d`

## pseudocode

```c
__int64 __fastcall AccessIfRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5,
        _DWORD *a6,
        int a7)
{
  int v9; // r13d
  unsigned int v12; // eax
  __int64 v13; // r12
  unsigned int v14; // ebx
  unsigned int InterfaceStatistics; // eax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  _DWORD *v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v18 = a3;
  v19 = a6;
  v17 = 0;
  v16 = 0;
  v9 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"Entered: %ws", L"AccessIfRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
  }
  if ( a7 == 87 )
    return 50;
  v12 = *a4;
  *a4 = 868;
  if ( v12 < 0x364 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIfRow");
    return 122;
  }
  *a5 = 2;
  v13 = 0;
  if ( a1 == 5 )
    RtlAcquireResourceExclusive(&Resource, 1u);
  else
    RtlAcquireResourceShared(&Resource, 1u);
  v14 = LocateIfRow(a1, (a2 >> 2) - 1, v18 + 4, &v17);
  if ( !v14 )
  {
    if ( a1 == 1 || a1 == 2 || a1 == 4 )
    {
      InterfaceStatistics = GetInterfaceStatistics(v17, a5 + 2);
    }
    else
    {
      if ( a1 != 5 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"AccessIfRow: Wrong query type %d", a1);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
        }
        v14 = 87;
        goto LABEL_25;
      }
      v13 = *(_QWORD *)(v17 + 184);
      InterfaceStatistics = SetInterfaceStatistics(v17, a5 + 2, &v16);
      v9 = v16;
    }
    v14 = InterfaceStatistics;
  }
LABEL_25:
  RtlReleaseResource(&Resource);
  if ( v9 )
    ((void (__fastcall *)(__int64, __int64, bool))EnableInterfaceWithDIM)(v13, 33, a5[137] == 1);
  *v19 = 1;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIfRow");
  return v14;
}

```

## disassembly

```asm
0x180004fd0  mov     [rsp-8+arg_8], rbx
0x180004fd5  push    rbp
0x180004fd6  push    rsi
0x180004fd7  push    rdi
0x180004fd8  push    r12
0x180004fda  push    r13
0x180004fdc  push    r14
0x180004fde  push    r15
0x180004fe0  lea     rbp, [rsp-760h]
0x180004fe8  sub     rsp, 860h
0x180004fef  mov     rax, cs:__security_cookie
0x180004ff6  xor     rax, rsp
0x180004ff9  mov     [rbp+790h+var_40], rax
0x180005000  mov     rax, [rbp+790h+arg_28]
0x180005007  xor     esi, esi
0x180005009  mov     r14, [rbp+790h+arg_20]
0x180005010  mov     r15d, edx
0x180005013  mov     [rsp+890h+var_850], r8
0x180005018  mov     edi, ecx
0x18000501a  xor     edx, edx; Val
0x18000501c  mov     [rsp+890h+var_848], rax
0x180005021  mov     r8d, 7FCh; Size
0x180005027  mov     [rsp+890h+var_858], rsi
0x18000502c  lea     rcx, [rsp+890h+var_83C]; void *
0x180005031  mov     [rsp+890h+var_860], esi
0x180005035  mov     r13d, esi
0x180005038  mov     [rsp+890h+var_840], esi
0x18000503c  mov     rbx, r9
0x18000503f  call    memset_0
0x180005044  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18000504b  jge     short loc_18000508B
0x18000504d  lea     r8, aAccessifrow; "AccessIfRow"
0x180005054  mov     word ptr [rsp+890h+var_840], si
0x180005059  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005060  lea     rcx, [rsp+890h+var_840]
0x180005065  call    FormatRRASErrorString
0x18000506a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180005071  jge     short loc_18000508B
0x180005073  lea     r8, [rsp+890h+var_840]
0x180005078  lea     rdx, RasRtrmgrTraceInfo
0x18000507f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005086  call    McTemplateU0z_EventWriteTransfer
0x18000508b  cmp     [rbp+790h+arg_30], 57h ; 'W'
0x180005092  jnz     short loc_18000509E
0x180005094  mov     eax, 32h ; '2'
0x180005099  jmp     loc_180005220
0x18000509e  mov     eax, [rbx]
0x1800050a0  mov     r8d, 364h
0x1800050a6  mov     [rbx], r8d
0x1800050a9  cmp     eax, r8d
0x1800050ac  jnb     short loc_1800050DB
0x1800050ae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800050b5  jz      short loc_1800050D1
0x1800050b7  lea     r8, aLeavingAccessi_9; "Leaving: AccessIfRow"
0x1800050be  lea     rdx, RasRtrmgrTraceInfo
0x1800050c5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800050cc  call    McTemplateU0z_EventWriteTransfer
0x1800050d1  mov     eax, 7Ah ; 'z'
0x1800050d6  jmp     loc_180005220
0x1800050db  mov     dword ptr [r14], 2
0x1800050e2  mov     r12, rsi
0x1800050e5  lea     rcx, Resource; Resource
0x1800050ec  mov     dl, 1; Wait
0x1800050ee  cmp     edi, 5
0x1800050f1  jnz     short loc_1800050FB
0x1800050f3  call    cs:__imp_RtlAcquireResourceExclusive
0x1800050f9  jmp     short loc_180005101
0x1800050fb  call    cs:__imp_RtlAcquireResourceShared
0x180005101  mov     r8, [rsp+890h+var_850]
0x180005106  lea     r9, [rsp+890h+var_858]
0x18000510b  shr     r15d, 2
0x18000510f  add     r8, 4
0x180005113  mov     ecx, edi
0x180005115  lea     edx, [r15-1]
0x180005119  call    LocateIfRow
0x18000511e  mov     ebx, eax
0x180005120  test    eax, eax
0x180005122  jnz     loc_1800051BB
0x180005128  mov     eax, edi
0x18000512a  sub     eax, 1
0x18000512d  jz      short loc_1800051AB
0x18000512f  sub     eax, 1
0x180005132  jz      short loc_1800051AB
0x180005134  sub     eax, 2
0x180005137  jz      short loc_1800051AB
0x180005139  cmp     eax, 1
0x18000513c  jz      short loc_18000518A
0x18000513e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180005145  jge     short loc_180005183
0x180005147  xor     eax, eax
0x180005149  lea     rdx, aAccessifrowWro; "AccessIfRow: Wrong query type %d"
0x180005150  mov     r8d, edi
0x180005153  mov     word ptr [rsp+890h+var_840], ax
0x180005158  lea     rcx, [rsp+890h+var_840]
0x18000515d  call    FormatRRASErrorString
0x180005162  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180005169  jge     short loc_180005183
0x18000516b  lea     r8, [rsp+890h+var_840]
0x180005170  lea     rdx, RasRtrmgrTraceInfo
0x180005177  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000517e  call    McTemplateU0z_EventWriteTransfer
0x180005183  mov     ebx, 57h ; 'W'
0x180005188  jmp     short loc_1800051BB
0x18000518a  mov     rcx, [rsp+890h+var_858]
0x18000518f  lea     r8, [rsp+890h+var_860]
0x180005194  lea     rdx, [r14+8]
0x180005198  mov     r12, [rcx+0B8h]
0x18000519f  call    SetInterfaceStatistics
0x1800051a4  mov     r13d, [rsp+890h+var_860]
0x1800051a9  jmp     short loc_1800051B9
0x1800051ab  mov     rcx, [rsp+890h+var_858]
0x1800051b0  lea     rdx, [r14+8]
0x1800051b4  call    GetInterfaceStatistics
0x1800051b9  mov     ebx, eax
0x1800051bb  lea     rcx, Resource; Resource
0x1800051c2  call    cs:__imp_RtlReleaseResource
0x1800051c8  test    r13d, r13d
0x1800051cb  jz      short loc_1800051F0
0x1800051cd  mov     rax, cs:EnableInterfaceWithDIM
0x1800051d4  xor     r8d, r8d
0x1800051d7  cmp     dword ptr [r14+224h], 1
0x1800051df  mov     edx, 21h ; '!'
0x1800051e4  mov     rcx, r12
0x1800051e7  setz    r8b
0x1800051eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f0  mov     rax, [rsp+890h+var_848]
0x1800051f5  mov     dword ptr [rax], 1
0x1800051fb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005202  jz      short loc_18000521E
0x180005204  lea     r8, aLeavingAccessi_9; "Leaving: AccessIfRow"
0x18000520b  lea     rdx, RasRtrmgrTraceInfo
0x180005212  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005219  call    McTemplateU0z_EventWriteTransfer
0x18000521e  mov     eax, ebx
0x180005220  mov     rcx, [rbp+790h+var_40]
0x180005227  xor     rcx, rsp; StackCookie
0x18000522a  call    __security_check_cookie
0x18000522f  mov     rbx, [rsp+890h+arg_8]
0x180005237  add     rsp, 860h
0x18000523e  pop     r15
0x180005240  pop     r14
0x180005242  pop     r13
0x180005244  pop     r12
0x180005246  pop     rdi
0x180005247  pop     rsi
0x180005248  pop     rbp
0x180005249  retn
```
