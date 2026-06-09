# CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)

- ea: `0x180030e2c`
- end: `0x180030fed`
- name: `?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z`
- size: `449`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031d50`

## callees

- `0x180030e2c`
- `0x180030ff4`
- `0x18003170c`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e8e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030e84`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030f07`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030e84`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180030f07`

## pseudocode

```c
signed int __fastcall CStowedExceptionPlugin::AddBlocksForStructure(CStowedExceptionPlugin *this, void *a2, void *a3)
{
  unsigned int v6; // r9d
  signed int result; // eax
  unsigned int v8; // r9d
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  unsigned __int64 v12; // r8
  void *v13; // rdx
  __int64 Buffer; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF
  void *v16[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v17; // [rsp+B8h] [rbp+40h] BYREF

  NumberOfBytesRead = 0;
  v17 = 0;
  Buffer = 0;
  memset(v16, 0, 40);
  if ( !ReadProcessMemory(a2, a3, &Buffer, 8u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 8 )
    return -2147024597;
  if ( (unsigned int)Buffer <= 8 )
    return -2147024883;
  CStowedExceptionPlugin::AddMemoryBlock(this, a3, Buffer, v6);
  if ( (unsigned int)Buffer < 0x28 || (unsigned int)(HIDWORD(Buffer) - 1397043249) > 1 )
    return 0;
  if ( ReadProcessMemory(a2, a3, v16, 0x28u, &NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead == 40 )
    {
      if ( LODWORD(v16[0]) >= 0x28 && (unsigned int)(HIDWORD(v16[0]) - 1397043249) <= 1 )
      {
        if ( (BYTE4(v16[1]) & 3) == 1 )
        {
          if ( !LODWORD(v16[3]) )
            return 0;
          if ( !HIDWORD(v16[3]) )
            return 0;
          v13 = v16[4];
          if ( !v16[4] )
            return 0;
          v12 = LODWORD(v16[3]) * (unsigned __int64)HIDWORD(v16[3]);
          if ( v12 > 0xFFFFFFFF || (unsigned int)v12 >= 0x7FFF8 )
            LODWORD(v12) = 524280;
          goto LABEL_30;
        }
        if ( (BYTE4(v16[1]) & 3) == 2 )
        {
          v9 = CStowedExceptionPlugin::CalculateRemoteStringLength(&v17, a2, v16[2], v8);
          if ( v9 < 0 )
          {
            if ( v9 != -805306106 )
              return 0;
            LODWORD(v12) = 0xFFFF;
          }
          else
          {
            v11 = v17;
            if ( 2 * (unsigned __int64)v17 > 0xFFFF )
              MicrosoftTelemetryAssertTriggeredNoArgs(v10);
            LODWORD(v12) = 2 * v11 + 2;
          }
          v13 = v16[2];
LABEL_30:
          CStowedExceptionPlugin::AddMemoryBlock(this, v13, v12, v8);
          return 0;
        }
      }
      return -2147024883;
    }
    return -2147024597;
  }
LABEL_2:
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180030e2c  push    rbp
0x180030e2e  push    rbx
0x180030e2f  push    rsi
0x180030e30  push    rdi
0x180030e31  mov     rbp, rsp
0x180030e34  sub     rsp, 78h
0x180030e38  xor     eax, eax
0x180030e3a  mov     [rbp+NumberOfBytesRead], 0
0x180030e42  mov     rdi, r8
0x180030e45  mov     [rbp+var_14], eax
0x180030e48  mov     rsi, rdx
0x180030e4b  mov     [rbp+arg_18], eax
0x180030e4e  xorps   xmm0, xmm0
0x180030e51  mov     [rbp+Buffer], 0
0x180030e59  lea     rax, [rbp+NumberOfBytesRead]
0x180030e5d  mov     [rbp+var_38], 0
0x180030e64  mov     rbx, rcx
0x180030e67  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180030e6c  mov     r9d, 8; nSize
0x180030e72  lea     r8, [rbp+Buffer]; lpBuffer
0x180030e76  mov     rdx, rdi; lpBaseAddress
0x180030e79  mov     rcx, rsi; hProcess
0x180030e7c  movups  xmmword ptr [rbp+var_34], xmm0
0x180030e80  movups  xmmword ptr [rbp+var_24], xmm0
0x180030e84  call    cs:__imp_ReadProcessMemory
0x180030e8a  test    eax, eax
0x180030e8c  jnz     short loc_180030EAF
0x180030e8e  call    cs:__imp_GetLastError
0x180030e94  test    eax, eax
0x180030e96  jle     short loc_180030EA0
0x180030e98  movzx   eax, ax
0x180030e9b  or      eax, 80070000h
0x180030ea0  test    eax, eax
0x180030ea2  mov     ecx, 80004005h
0x180030ea7  cmovns  eax, ecx
0x180030eaa  jmp     loc_180030FE4
0x180030eaf  cmp     [rbp+NumberOfBytesRead], 8
0x180030eb4  jnz     loc_180030FDF
0x180030eba  mov     r8, [rbp+Buffer]; unsigned int
0x180030ebe  cmp     r8d, 8
0x180030ec2  jbe     loc_180030FD8
0x180030ec8  mov     rdx, rdi; void *
0x180030ecb  mov     rcx, rbx; this
0x180030ece  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x180030ed3  cmp     dword ptr [rbp+Buffer], 28h ; '('
0x180030ed7  jb      loc_180030FD4
0x180030edd  mov     eax, dword ptr [rbp+Buffer+4]
0x180030ee0  add     eax, 0ACBACFCFh
0x180030ee5  cmp     eax, 1
0x180030ee8  ja      loc_180030FD4
0x180030eee  lea     rax, [rbp+NumberOfBytesRead]
0x180030ef2  mov     r9d, 28h ; '('; nSize
0x180030ef8  lea     r8, [rbp+var_38]; lpBuffer
0x180030efc  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180030f01  mov     rdx, rdi; lpBaseAddress
0x180030f04  mov     rcx, rsi; hProcess
0x180030f07  call    cs:__imp_ReadProcessMemory
0x180030f0d  test    eax, eax
0x180030f0f  jz      loc_180030E8E
0x180030f15  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x180030f1a  jnz     loc_180030FDF
0x180030f20  cmp     [rbp+var_38], 28h ; '('
0x180030f24  jb      loc_180030FD8
0x180030f2a  mov     eax, dword ptr [rbp+var_34]
0x180030f2d  add     eax, 0ACBACFCFh
0x180030f32  cmp     eax, 1
0x180030f35  ja      loc_180030FD8
0x180030f3b  mov     eax, dword ptr [rbp+var_34+8]
0x180030f3e  and     eax, 3
0x180030f41  sub     eax, 1
0x180030f44  jz      short loc_180030F95
0x180030f46  cmp     eax, 1
0x180030f49  jnz     loc_180030FD8
0x180030f4f  mov     r8, [rbp+var_34+0Ch]; void *
0x180030f53  lea     rcx, [rbp+arg_18]; unsigned int *
0x180030f57  mov     rdx, rsi; void *
0x180030f5a  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x180030f5f  test    eax, eax
0x180030f61  js      short loc_180030F86
0x180030f63  mov     edi, [rbp+arg_18]
0x180030f66  mov     eax, edi
0x180030f68  add     rax, rax
0x180030f6b  cmp     rax, 0FFFFh
0x180030f71  jbe     short loc_180030F78
0x180030f73  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030f78  lea     r8d, ds:2[rdi*2]
0x180030f80  mov     rdx, [rbp+var_34+0Ch]
0x180030f84  jmp     short loc_180030FCC
0x180030f86  cmp     eax, 0D0000106h
0x180030f8b  jnz     short loc_180030FD4
0x180030f8d  mov     r8d, 0FFFFh
0x180030f93  jmp     short loc_180030F80
0x180030f95  mov     eax, dword ptr [rbp+var_24+4]
0x180030f98  test    eax, eax
0x180030f9a  jz      short loc_180030FD4
0x180030f9c  mov     ecx, dword ptr [rbp+var_24+8]
0x180030f9f  test    ecx, ecx
0x180030fa1  jz      short loc_180030FD4
0x180030fa3  mov     rdx, [rbp+var_24+0Ch]; void *
0x180030fa7  test    rdx, rdx
0x180030faa  jz      short loc_180030FD4
0x180030fac  mov     r8d, ecx
0x180030faf  imul    r8, rax
0x180030fb3  mov     eax, 0FFFFFFFFh
0x180030fb8  cmp     r8, rax
0x180030fbb  ja      short loc_180030FC6
0x180030fbd  cmp     r8d, 7FFF8h
0x180030fc4  jb      short loc_180030FCC
0x180030fc6  mov     r8d, 7FFF8h; unsigned int
0x180030fcc  mov     rcx, rbx; this
0x180030fcf  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x180030fd4  xor     eax, eax
0x180030fd6  jmp     short loc_180030FE4
0x180030fd8  mov     eax, 8007000Dh
0x180030fdd  jmp     short loc_180030FE4
0x180030fdf  mov     eax, 8007012Bh
0x180030fe4  add     rsp, 78h
0x180030fe8  pop     rdi
0x180030fe9  pop     rsi
0x180030fea  pop     rbx
0x180030feb  pop     rbp
0x180030fec  retn
```
