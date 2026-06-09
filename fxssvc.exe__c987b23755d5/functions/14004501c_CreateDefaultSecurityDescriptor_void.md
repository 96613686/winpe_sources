# CreateDefaultSecurityDescriptor(void)

- ea: `0x14004501c`
- end: `0x1400452a3`
- name: `?CreateDefaultSecurityDescriptor@@YAKXZ`
- size: `647`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400458d0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14004501c`
- `0x140045c88`
- `0x140070f1c`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400450a6`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400450a6`
- `ADVAPI32!DestroyPrivateObjectSecurity` at `0x140045253`
- `ADVAPI32!DestroyPrivateObjectSecurity` at `0x140045253`
- `ADVAPI32!OpenProcessToken` at `0x140045107`
- `ADVAPI32!OpenProcessToken` at `0x140045107`
- `ADVAPI32!CreatePrivateObjectSecurity` at `0x140045178`
- `ADVAPI32!CreatePrivateObjectSecurity` at `0x140045178`
- `KERNEL32!GetLastError` at `0x1400450b0`
- `KERNEL32!GetLastError` at `0x140045111`
- `KERNEL32!GetLastError` at `0x140045182`
- `KERNEL32!GetLastError` at `0x140045227`
- `KERNEL32!GetLastError` at `0x140045275`
- `KERNEL32!GetLastError` at `0x1400450b0`
- `KERNEL32!GetLastError` at `0x140045111`
- `KERNEL32!GetLastError` at `0x140045182`
- `KERNEL32!GetLastError` at `0x140045227`
- `KERNEL32!GetLastError` at `0x140045275`
- `KERNEL32!CloseHandle` at `0x140045205`
- `KERNEL32!CloseHandle` at `0x140045205`
- `KERNEL32!LocalFree` at `0x1400451f6`
- `KERNEL32!LocalFree` at `0x1400451f6`
- `KERNEL32!GetCurrentProcess` at `0x1400450f5`
- `KERNEL32!GetCurrentProcess` at `0x1400450f5`

## pseudocode

```c
__int64 CreateDefaultSecurityDescriptor(void)
{
  int v0; // eax
  const WCHAR *v1; // rcx
  DWORD LastError; // eax
  DWORD v3; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v5; // eax
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  DWORD v9; // eax
  ULONG SecurityDescriptorSize; // [rsp+60h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+68h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+40h] BYREF

  SecurityDescriptor = 0;
  NewDescriptor = 0;
  SecurityDescriptorSize = 0;
  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v0 = IsServerSku();
  v1 = L"O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;;;WD)(A;;0x20227;;;IU)";
  if ( v0 )
    v1 = L"O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;;;WD)";
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v1, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
    goto LABEL_29;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v5 = GetLastError();
    v3 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v7 = 32;
    goto LABEL_17;
  }
  if ( !CreatePrivateObjectSecurity(
          0,
          SecurityDescriptor,
          &NewDescriptor,
          0,
          TokenHandle,
          (PGENERIC_MAPPING)&GenericMapping) )
  {
    v5 = GetLastError();
    v3 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v7 = 33;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v5);
    goto LABEL_29;
  }
  v5 = SaveSecurityDescriptor(NewDescriptor);
  v3 = v5;
  if ( !v5 )
  {
    g_pFaxSD = NewDescriptor;
    NewDescriptor = 0;
    goto LABEL_29;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 34;
    goto LABEL_17;
  }
LABEL_29:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v8);
  }
  if ( NewDescriptor
    && !DestroyPrivateObjectSecurity(&NewDescriptor)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v9);
  }
  return v3;
}

```

## disassembly

```asm
0x14004501c  push    rbp
0x14004501e  push    rbx
0x14004501f  push    r12
0x140045021  push    r14
0x140045023  mov     rbp, rsp
0x140045026  sub     rsp, 38h
0x14004502a  mov     [rbp+SecurityDescriptor], 0
0x140045032  mov     [rbp+NewDescriptor], 0
0x14004503a  mov     [rbp+SecurityDescriptorSize], 0
0x140045041  mov     [rbp+TokenHandle], 0
0x140045049  mov     rcx, cs:WPP_GLOBAL_Control
0x140045050  lea     r14, WPP_GLOBAL_Control
0x140045057  lea     r12, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004505e  cmp     rcx, r14
0x140045061  jz      short loc_140045080
0x140045063  test    byte ptr [rcx+1Ch], 4
0x140045067  jz      short loc_140045080
0x140045069  cmp     byte ptr [rcx+19h], 5
0x14004506d  jb      short loc_140045080
0x14004506f  mov     rcx, [rcx+10h]
0x140045073  mov     edx, 1Eh
0x140045078  mov     r8, r12
0x14004507b  call    WPP_SF_
0x140045080  call    IsServerSku
0x140045085  lea     rdx, aONsgNsdA0xe02e; "O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;"...
0x14004508c  test    eax, eax
0x14004508e  lea     rcx, aONsgNsdA0xe02e_0; "O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;"...
0x140045095  cmovnz  rcx, rdx; StringSecurityDescriptor
0x140045099  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x14004509d  mov     edx, 1; StringSDRevision
0x1400450a2  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400450a6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400450ac  test    eax, eax
0x1400450ae  jnz     short loc_1400450F5
0x1400450b0  call    cs:__imp_GetLastError
0x1400450b6  mov     ebx, eax
0x1400450b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400450bf  cmp     rcx, r14
0x1400450c2  jz      loc_1400451ED
0x1400450c8  test    byte ptr [rcx+1Ch], 4
0x1400450cc  jz      loc_1400451ED
0x1400450d2  cmp     byte ptr [rcx+19h], 2
0x1400450d6  jb      loc_1400451ED
0x1400450dc  mov     rcx, [rcx+10h]
0x1400450e0  mov     edx, 1Fh
0x1400450e5  mov     r9d, eax
0x1400450e8  mov     r8, r12
0x1400450eb  call    WPP_SF_d
0x1400450f0  jmp     loc_1400451ED
0x1400450f5  call    cs:__imp_GetCurrentProcess
0x1400450fb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400450ff  mov     edx, 8; DesiredAccess
0x140045104  mov     rcx, rax; ProcessHandle
0x140045107  call    cs:__imp_OpenProcessToken
0x14004510d  test    eax, eax
0x14004510f  jnz     short loc_140045156
0x140045111  call    cs:__imp_GetLastError
0x140045117  mov     ebx, eax
0x140045119  mov     rcx, cs:WPP_GLOBAL_Control
0x140045120  cmp     rcx, r14
0x140045123  jz      loc_1400451ED
0x140045129  test    byte ptr [rcx+1Ch], 4
0x14004512d  jz      loc_1400451ED
0x140045133  cmp     byte ptr [rcx+19h], 2
0x140045137  jb      loc_1400451ED
0x14004513d  mov     edx, 20h ; ' '
0x140045142  mov     rcx, [rcx+10h]
0x140045146  mov     r9d, eax
0x140045149  mov     r8, r12
0x14004514c  call    WPP_SF_d
0x140045151  jmp     loc_1400451ED
0x140045156  mov     rdx, [rbp+SecurityDescriptor]; CreatorDescriptor
0x14004515a  lea     rax, GenericMapping
0x140045161  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x140045166  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x14004516a  mov     rax, [rbp+TokenHandle]
0x14004516e  xor     r9d, r9d; IsDirectoryObject
0x140045171  xor     ecx, ecx; ParentDescriptor
0x140045173  mov     [rsp+38h+Token], rax; Token
0x140045178  call    cs:__imp_CreatePrivateObjectSecurity
0x14004517e  test    eax, eax
0x140045180  jnz     short loc_1400451A9
0x140045182  call    cs:__imp_GetLastError
0x140045188  mov     ebx, eax
0x14004518a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045191  cmp     rcx, r14
0x140045194  jz      short loc_1400451ED
0x140045196  test    byte ptr [rcx+1Ch], 4
0x14004519a  jz      short loc_1400451ED
0x14004519c  cmp     byte ptr [rcx+19h], 2
0x1400451a0  jb      short loc_1400451ED
0x1400451a2  mov     edx, 21h ; '!'
0x1400451a7  jmp     short loc_140045142
0x1400451a9  mov     rcx, [rbp+NewDescriptor]; pAbsoluteSecurityDescriptor
0x1400451ad  call    ?SaveSecurityDescriptor@@YAKPEAX@Z; SaveSecurityDescriptor(void *)
0x1400451b2  mov     ebx, eax
0x1400451b4  test    eax, eax
0x1400451b6  jz      short loc_1400451DA
0x1400451b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451bf  cmp     rcx, r14
0x1400451c2  jz      short loc_1400451ED
0x1400451c4  test    byte ptr [rcx+1Ch], 4
0x1400451c8  jz      short loc_1400451ED
0x1400451ca  cmp     byte ptr [rcx+19h], 2
0x1400451ce  jb      short loc_1400451ED
0x1400451d0  mov     edx, 22h ; '"'
0x1400451d5  jmp     loc_140045142
0x1400451da  mov     rax, [rbp+NewDescriptor]
0x1400451de  mov     cs:?g_pFaxSD@@3PEAXEA, rax; void * g_pFaxSD
0x1400451e5  mov     [rbp+NewDescriptor], 0
0x1400451ed  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1400451f1  test    rcx, rcx
0x1400451f4  jz      short loc_1400451FC
0x1400451f6  call    cs:__imp_LocalFree
0x1400451fc  mov     rcx, [rbp+TokenHandle]; hObject
0x140045200  test    rcx, rcx
0x140045203  jz      short loc_140045248
0x140045205  call    cs:__imp_CloseHandle
0x14004520b  test    eax, eax
0x14004520d  jnz     short loc_140045248
0x14004520f  mov     rax, cs:WPP_GLOBAL_Control
0x140045216  cmp     rax, r14
0x140045219  jz      short loc_140045248
0x14004521b  test    byte ptr [rax+1Ch], 4
0x14004521f  jz      short loc_140045248
0x140045221  cmp     byte ptr [rax+19h], 2
0x140045225  jb      short loc_140045248
0x140045227  call    cs:__imp_GetLastError
0x14004522d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045234  mov     edx, 23h ; '#'
0x140045239  mov     r9d, eax
0x14004523c  mov     r8, r12
0x14004523f  mov     rcx, [rcx+10h]
0x140045243  call    WPP_SF_d
0x140045248  cmp     [rbp+NewDescriptor], 0
0x14004524d  jz      short loc_140045296
0x14004524f  lea     rcx, [rbp+NewDescriptor]; ObjectDescriptor
0x140045253  call    cs:__imp_DestroyPrivateObjectSecurity
0x140045259  test    eax, eax
0x14004525b  jnz     short loc_140045296
0x14004525d  mov     rax, cs:WPP_GLOBAL_Control
0x140045264  cmp     rax, r14
0x140045267  jz      short loc_140045296
0x140045269  test    byte ptr [rax+1Ch], 4
0x14004526d  jz      short loc_140045296
0x14004526f  cmp     byte ptr [rax+19h], 2
0x140045273  jb      short loc_140045296
0x140045275  call    cs:__imp_GetLastError
0x14004527b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045282  mov     edx, 24h ; '$'
0x140045287  mov     r9d, eax
0x14004528a  mov     r8, r12
0x14004528d  mov     rcx, [rcx+10h]
0x140045291  call    WPP_SF_d
0x140045296  mov     eax, ebx
0x140045298  add     rsp, 38h
0x14004529c  pop     r14
0x14004529e  pop     r12
0x1400452a0  pop     rbx
0x1400452a1  pop     rbp
0x1400452a2  retn
```
