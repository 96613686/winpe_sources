# SecWriteFileDlpEA

- ea: `0x140022fe4`
- end: `0x14002314c`
- name: `SecWriteFileDlpEA`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140021ca0`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x140022fe4`
- `0x140028f9c`
- `0x14002975c`
- `0x140030020`
- `0x140030550`
- `0x14003ba4c`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x140023030`
- `ntoskrnl!ObfDereferenceObject` at `0x140023115`
- `ntoskrnl!ObfDereferenceObject` at `0x140023115`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002305f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002305f`

## pseudocode

```c
__int64 __fastcall SecWriteFileDlpEA(unsigned __int64 a1, __int64 a2)
{
  char v4; // di
  void *v5; // rcx
  NTSTATUS IsRemoteFile; // ebx
  __int64 v7; // rdx
  _WORD *v8; // r8
  PVOID Object; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v11[4]; // [rsp+38h] [rbp-51h] BYREF
  ULONG v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  _BYTE FileInformation[128]; // [rsp+40h] [rbp-49h] BYREF

  Object = 0;
  v11[0] = 0;
  v4 = 0;
  memset(FileInformation, 0, 0x74u);
  v5 = *(void **)(a1 + 16);
  v12 = 0;
  IsRemoteFile = ObReferenceObjectByHandle(v5, 0x1F0000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( IsRemoteFile >= 0 )
  {
    if ( SecCacheIsFileEaCacheable((PFILE_OBJECT)Object) )
      goto LABEL_10;
    IsRemoteFile = SecIsRemoteFile(Object, v11);
    if ( IsRemoteFile >= 0 && v11[0] )
    {
      IsRemoteFile = SecQueryInformationFile(
                       (PFILE_OBJECT)Object,
                       FileInformation,
                       0x74u,
                       FileRemoteProtocolInformation,
                       &v12);
      if ( IsRemoteFile >= 0 )
        v4 = FileInformation[16] & 1;
      if ( v11[0] && (v4 || (unsigned __int8)SecIsWriteRemoteFileEaEnabled()) )
      {
LABEL_10:
        v8 = (_WORD *)(a1 + *(_QWORD *)(a1 + 32));
        if ( (unsigned __int64)v8 < a1 )
        {
          IsRemoteFile = -1073741675;
        }
        else if ( *v8 == 1 )
        {
          LOBYTE(v7) = *(_BYTE *)(a1 + 24);
          IsRemoteFile = SecCacheSetFileDlpEa(Object, v7);
        }
        else
        {
          IsRemoteFile = -1073741811;
        }
      }
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  *(_DWORD *)(a2 + 16) = IsRemoteFile;
  return (unsigned int)IsRemoteFile;
}

```

## disassembly

```asm
0x140022fe4  mov     [rsp-8+arg_10], rbx
0x140022fe9  mov     [rsp-8+arg_18], rsi
0x140022fee  push    rbp
0x140022fef  push    rdi
0x140022ff0  push    r14
0x140022ff2  lea     rbp, [rsp-47h]
0x140022ff7  sub     rsp, 0D0h
0x140022ffe  mov     rax, cs:__security_cookie
0x140023005  xor     rax, rsp
0x140023008  mov     [rbp+57h+var_20], rax
0x14002300c  mov     r14, rdx
0x14002300f  mov     [rbp+57h+var_B0], 0
0x140023017  xor     edx, edx; Val
0x140023019  mov     [rbp+57h+var_A8], 0
0x14002301d  mov     rsi, rcx
0x140023020  xor     dil, dil
0x140023023  lea     rcx, [rbp+57h+FileInformation]; void *
0x140023027  lea     r8d, [rdx+74h]; Size
0x14002302b  call    memset
0x140023030  mov     r8, cs:__imp_IoFileObjectType
0x140023037  lea     rax, [rbp+57h+var_B0]
0x14002303b  mov     rcx, [rsi+10h]; Handle
0x14002303f  xor     r9d, r9d; AccessMode
0x140023042  mov     [rbp+57h+var_A4], 0
0x140023049  mov     edx, 1F0000h; DesiredAccess
0x14002304e  mov     [rsp+0E0h+HandleInformation], 0; HandleInformation
0x140023057  mov     r8, [r8]; ObjectType
0x14002305a  mov     [rsp+0E0h+Object], rax; Object
0x14002305f  call    cs:__imp_ObReferenceObjectByHandle
0x140023066  nop     dword ptr [rax+rax+00h]
0x14002306b  mov     ebx, eax
0x14002306d  test    eax, eax
0x14002306f  js      loc_14002310C
0x140023075  mov     rcx, [rbp+57h+var_B0]; FileObject
0x140023079  call    SecCacheIsFileEaCacheable
0x14002307e  test    al, al
0x140023080  jnz     short loc_1400230DD
0x140023082  mov     rcx, [rbp+57h+var_B0]
0x140023086  lea     rdx, [rbp+57h+var_A8]
0x14002308a  call    SecIsRemoteFile
0x14002308f  mov     ebx, eax
0x140023091  test    eax, eax
0x140023093  js      short loc_14002310C
0x140023095  cmp     [rbp+57h+var_A8], dil
0x140023099  jz      short loc_14002310C
0x14002309b  mov     rcx, [rbp+57h+var_B0]; FileObject
0x14002309f  lea     rax, [rbp+57h+var_A4]
0x1400230a3  mov     r9d, 37h ; '7'; FileInformationClass
0x1400230a9  mov     [rsp+0E0h+Object], rax; PULONG
0x1400230ae  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x1400230b2  lea     r8d, [r9+3Dh]; Length
0x1400230b6  call    SecQueryInformationFile
0x1400230bb  mov     ebx, eax
0x1400230bd  test    eax, eax
0x1400230bf  js      short loc_1400230C9
0x1400230c1  mov     dil, [rbp+57h+var_90]
0x1400230c5  and     dil, 1
0x1400230c9  cmp     [rbp+57h+var_A8], 0
0x1400230cd  jz      short loc_14002310C
0x1400230cf  test    dil, dil
0x1400230d2  jnz     short loc_1400230DD
0x1400230d4  call    SecIsWriteRemoteFileEaEnabled
0x1400230d9  test    al, al
0x1400230db  jz      short loc_14002310C
0x1400230dd  mov     r8, [rsi+20h]
0x1400230e1  add     r8, rsi
0x1400230e4  cmp     r8, rsi
0x1400230e7  jb      short loc_140023107
0x1400230e9  cmp     word ptr [r8], 1
0x1400230ee  jz      short loc_1400230F7
0x1400230f0  mov     ebx, 0C000000Dh
0x1400230f5  jmp     short loc_14002310C
0x1400230f7  mov     dl, [rsi+18h]
0x1400230fa  mov     rcx, [rbp+57h+var_B0]
0x1400230fe  call    SecCacheSetFileDlpEa
0x140023103  mov     ebx, eax
0x140023105  jmp     short loc_14002310C
0x140023107  mov     ebx, 0C0000095h
0x14002310c  mov     rcx, [rbp+57h+var_B0]; Object
0x140023110  test    rcx, rcx
0x140023113  jz      short loc_140023121
0x140023115  call    cs:__imp_ObfDereferenceObject
0x14002311c  nop     dword ptr [rax+rax+00h]
0x140023121  mov     [r14+10h], ebx
0x140023125  mov     eax, ebx
0x140023127  mov     rcx, [rbp+57h+var_20]
0x14002312b  xor     rcx, rsp; StackCookie
0x14002312e  call    __security_check_cookie
0x140023133  lea     r11, [rsp+0E0h+var_10]
0x14002313b  mov     rbx, [r11+30h]
0x14002313f  mov     rsi, [r11+38h]
0x140023143  mov     rsp, r11
0x140023146  pop     r14
0x140023148  pop     rdi
0x140023149  pop     rbp
0x14002314a  retn
```
