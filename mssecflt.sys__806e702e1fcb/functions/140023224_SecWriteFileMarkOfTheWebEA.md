# SecWriteFileMarkOfTheWebEA

- ea: `0x140023224`
- end: `0x1400233b4`
- name: `SecWriteFileMarkOfTheWebEA`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140021ca0`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x140023224`
- `0x140028f9c`
- `0x14002975c`
- `0x140030020`
- `0x140030580`
- `0x14003b670`
- `0x14003ba4c`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14002327d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002337d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002337d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400232a1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400232a1`

## pseudocode

```c
__int64 __fastcall SecWriteFileMarkOfTheWebEA(unsigned __int64 a1, __int64 a2)
{
  NTSTATUS IsRemoteFile; // ebx
  char v5; // si
  unsigned __int64 v6; // rcx
  _WORD *v7; // r8
  int Object; // [rsp+20h] [rbp-69h]
  PVOID v10; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v11[4]; // [rsp+38h] [rbp-51h] BYREF
  ULONG v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  _BYTE FileInformation[128]; // [rsp+40h] [rbp-49h] BYREF

  IsRemoteFile = 0;
  v10 = 0;
  v11[0] = 0;
  v5 = 0;
  memset(FileInformation, 0, 0x74u);
  v12 = 0;
  if ( (unsigned __int8)SecIsFileSourceMonitoringEnabled() )
  {
    IsRemoteFile = ObReferenceObjectByHandle(
                     *(HANDLE *)(a1 + 16),
                     0x120116u,
                     (POBJECT_TYPE)IoFileObjectType,
                     1,
                     &v10,
                     0);
    if ( IsRemoteFile >= 0 )
    {
      if ( (unsigned __int8)SecCacheIsFileEaCacheable((PFILE_OBJECT)v10) )
        goto LABEL_11;
      IsRemoteFile = SecIsRemoteFile(v10, v11);
      if ( IsRemoteFile >= 0 && v11[0] )
      {
        IsRemoteFile = SecQueryInformationFile(
                         (PFILE_OBJECT)v10,
                         FileInformation,
                         0x74u,
                         FileRemoteProtocolInformation,
                         &v12);
        if ( IsRemoteFile >= 0 )
          v5 = FileInformation[16] & 1;
        if ( v11[0] && (v5 || (unsigned __int8)SecIsWriteRemoteFileEaEnabled()) )
        {
LABEL_11:
          v6 = *(_QWORD *)(a1 + 24);
          if ( *(unsigned int *)(a1 + 8) < v6 )
          {
LABEL_12:
            IsRemoteFile = -1073741811;
            goto LABEL_17;
          }
          v7 = (_WORD *)(v6 + a1);
          if ( v6 + a1 < a1 )
          {
            IsRemoteFile = -1073741675;
          }
          else
          {
            if ( *v7 != 1 )
              goto LABEL_12;
            _mm_lfence();
            LOBYTE(Object) = 0;
            IsRemoteFile = SecCacheSetFileEa(
                             v10,
                             &SecCacheFileMarkOfTheWebEAName,
                             v7,
                             (unsigned int)(unsigned __int16)v7[1] + 6,
                             Object);
          }
        }
      }
    }
  }
LABEL_17:
  if ( v10 )
    ObfDereferenceObject(v10);
  *(_DWORD *)(a2 + 16) = IsRemoteFile;
  return (unsigned int)IsRemoteFile;
}

```

## disassembly

```asm
0x140023224  mov     [rsp-8+arg_10], rbx
0x140023229  mov     [rsp-8+arg_18], rsi
0x14002322e  push    rbp
0x14002322f  push    rdi
0x140023230  push    r14
0x140023232  lea     rbp, [rsp-47h]
0x140023237  sub     rsp, 0D0h
0x14002323e  mov     rax, cs:__security_cookie
0x140023245  xor     rax, rsp
0x140023248  mov     [rbp+57h+var_20], rax
0x14002324c  xor     ebx, ebx
0x14002324e  mov     r14, rdx
0x140023251  mov     rdi, rcx
0x140023254  mov     [rbp+57h+var_B0], rbx
0x140023258  xor     edx, edx; Val
0x14002325a  mov     [rbp+57h+var_A8], bl
0x14002325d  lea     rcx, [rbp+57h+FileInformation]; void *
0x140023261  xor     sil, sil
0x140023264  lea     r8d, [rbx+74h]; Size
0x140023268  call    memset
0x14002326d  mov     [rbp+57h+var_A4], ebx
0x140023270  call    SecIsFileSourceMonitoringEnabled
0x140023275  test    al, al
0x140023277  jz      loc_140023374
0x14002327d  mov     r8, cs:__imp_IoFileObjectType
0x140023284  lea     rax, [rbp+57h+var_B0]
0x140023288  mov     rcx, [rdi+10h]; Handle
0x14002328c  mov     r9b, 1; AccessMode
0x14002328f  mov     [rsp+0E0h+HandleInformation], rbx; HandleInformation
0x140023294  mov     edx, 120116h; DesiredAccess
0x140023299  mov     [rsp+0E0h+Object], rax; Object
0x14002329e  mov     r8, [r8]; ObjectType
0x1400232a1  call    cs:__imp_ObReferenceObjectByHandle
0x1400232a8  nop     dword ptr [rax+rax+00h]
0x1400232ad  mov     ebx, eax
0x1400232af  test    eax, eax
0x1400232b1  js      loc_140023374
0x1400232b7  mov     rcx, [rbp+57h+var_B0]; FileObject
0x1400232bb  call    SecCacheIsFileEaCacheable
0x1400232c0  test    al, al
0x1400232c2  jnz     short loc_140023327
0x1400232c4  mov     rcx, [rbp+57h+var_B0]
0x1400232c8  lea     rdx, [rbp+57h+var_A8]
0x1400232cc  call    SecIsRemoteFile
0x1400232d1  mov     ebx, eax
0x1400232d3  test    eax, eax
0x1400232d5  js      loc_140023374
0x1400232db  cmp     [rbp+57h+var_A8], sil
0x1400232df  jz      loc_140023374
0x1400232e5  mov     rcx, [rbp+57h+var_B0]; FileObject
0x1400232e9  lea     rax, [rbp+57h+var_A4]
0x1400232ed  mov     r9d, 37h ; '7'; FileInformationClass
0x1400232f3  mov     [rsp+0E0h+Object], rax; PULONG
0x1400232f8  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x1400232fc  lea     r8d, [r9+3Dh]; Length
0x140023300  call    SecQueryInformationFile
0x140023305  mov     ebx, eax
0x140023307  test    eax, eax
0x140023309  js      short loc_140023313
0x14002330b  mov     sil, [rbp+57h+var_90]
0x14002330f  and     sil, 1
0x140023313  cmp     [rbp+57h+var_A8], 0
0x140023317  jz      short loc_140023374
0x140023319  test    sil, sil
0x14002331c  jnz     short loc_140023327
0x14002331e  call    SecIsWriteRemoteFileEaEnabled
0x140023323  test    al, al
0x140023325  jz      short loc_140023374
0x140023327  mov     rcx, [rdi+18h]
0x14002332b  mov     eax, [rdi+8]
0x14002332e  cmp     rax, rcx
0x140023331  jnb     short loc_14002333A
0x140023333  mov     ebx, 0C000000Dh
0x140023338  jmp     short loc_140023374
0x14002333a  lea     r8, [rcx+rdi]
0x14002333e  cmp     r8, rdi
0x140023341  jb      short loc_14002336F
0x140023343  cmp     word ptr [r8], 1
0x140023348  jnz     short loc_140023333
0x14002334a  lfence
0x14002334d  movzx   r9d, word ptr [r8+2]
0x140023352  lea     rdx, SecCacheFileMarkOfTheWebEAName
0x140023359  mov     rcx, [rbp+57h+var_B0]
0x14002335d  add     r9d, 6
0x140023361  mov     byte ptr [rsp+0E0h+Object], 0
0x140023366  call    SecCacheSetFileEa
0x14002336b  mov     ebx, eax
0x14002336d  jmp     short loc_140023374
0x14002336f  mov     ebx, 0C0000095h
0x140023374  mov     rcx, [rbp+57h+var_B0]; Object
0x140023378  test    rcx, rcx
0x14002337b  jz      short loc_140023389
0x14002337d  call    cs:__imp_ObfDereferenceObject
0x140023384  nop     dword ptr [rax+rax+00h]
0x140023389  mov     [r14+10h], ebx
0x14002338d  mov     eax, ebx
0x14002338f  mov     rcx, [rbp+57h+var_20]
0x140023393  xor     rcx, rsp; StackCookie
0x140023396  call    __security_check_cookie
0x14002339b  lea     r11, [rsp+0E0h+var_10]
0x1400233a3  mov     rbx, [r11+30h]
0x1400233a7  mov     rsi, [r11+38h]
0x1400233ab  mov     rsp, r11
0x1400233ae  pop     r14
0x1400233b0  pop     rdi
0x1400233b1  pop     rbp
0x1400233b2  retn
```
