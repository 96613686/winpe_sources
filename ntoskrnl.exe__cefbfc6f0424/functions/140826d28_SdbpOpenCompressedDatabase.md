# SdbpOpenCompressedDatabase

- ea: `0x140826d28`
- end: `0x140826ee8`
- name: `SdbpOpenCompressedDatabase`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140821914`

## callees

- `0x1406eb0e0`
- `0x140826d28`
- `0x1408bebe8`
- `0x1408bf658`
- `0x1408c1224`
- `0x1408c14bc`
- `0x1408c2d0c`
- `0x1408c2f88`

## string_xrefs

- `0x140826ec0`: `Failed to read expanded database header`
- `0x140826ded`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`
- `0x140826dae`: `SDB is not compressed`
- `0x140826dc8`: `SDB compression algorithm does not match callback algorithm.`
- `0x140826d72`: `SdbpOpenCompressedDatabase`
- `0x140826e34`: `SdbpOpenCompressedDatabase`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(__int64 *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebp
  __int64 v4; // rbx
  __int64 v8; // r14
  _DWORD *v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 result; // rax
  __int64 v13; // rax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v14 = 0;
  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    *(_DWORD *)(a2 + 8) = 0;
  }
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpOpenCompressedDatabase",
      175,
      (unsigned int)"No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_18;
  }
  v8 = *a1;
  if ( *(_DWORD *)(*a1 + 20) >= 0x14u )
  {
    v9 = *(_DWORD **)(v8 + 8);
    if ( v9[2] == 1717724282 )
    {
      if ( v9[3] == g_ExpectedAlgorithm )
      {
        v14 = v9[4];
        v10 = AslAlloc(v9, v14);
        if ( v10 )
        {
          if ( (unsigned int)guard_dispatch_icall_no_overrides(
                               v10,
                               &v14,
                               *(_QWORD *)(v8 + 8) + 20LL,
                               (unsigned int)(*(_DWORD *)(v8 + 20) - 20)) )
          {
            v13 = SdbpOpenDatabaseInMemory(v10, v14, a3);
            v4 = v13;
            if ( v13 )
            {
              *(_DWORD *)(v13 + 24) |= 4u;
              if ( !a2 || (unsigned int)SdbpReadMappedData(v13, 0, a2, 12) )
              {
                *(_DWORD *)(v4 + 24) |= 8u;
                v3 = 1;
                v14 = 0;
                goto LABEL_18;
              }
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpOpenCompressedDatabase",
                238,
                (unsigned int)"Failed to read expanded database header");
            }
          }
          else
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"SdbpOpenCompressedDatabase",
              221,
              (unsigned int)"Expand callback failed to expand SDB");
          }
          AslFree(v11, v10);
          v14 = 0;
          if ( v4 )
          {
            *(_QWORD *)(v4 + 8) = 0;
            SdbCloseDatabaseRead(v4);
            v4 = 0;
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpOpenCompressedDatabase",
            211,
            (unsigned int)"SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpOpenCompressedDatabase",
          192,
          (unsigned int)"SDB compression algorithm does not match callback algorithm.");
      }
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"SdbpOpenCompressedDatabase", 187, (unsigned int)"SDB is not compressed");
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenCompressedDatabase", 180, (unsigned int)"SDB file too small to be valid");
  }
LABEL_18:
  SdbCloseDatabaseRead(*a1);
  result = v3;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140826d28  mov     [rsp+arg_8], rbx
0x140826d2d  mov     [rsp+arg_10], rbp
0x140826d32  push    rsi
0x140826d33  push    rdi
0x140826d34  push    r12
0x140826d36  push    r14
0x140826d38  push    r15
0x140826d3a  sub     rsp, 30h
0x140826d3e  xor     ebp, ebp
0x140826d40  xor     ebx, ebx
0x140826d42  mov     [rsp+58h+arg_0], ebp
0x140826d46  mov     r12d, r8d
0x140826d49  mov     rdi, rdx
0x140826d4c  mov     r15, rcx
0x140826d4f  test    rdx, rdx
0x140826d52  jz      short loc_140826D5C
0x140826d54  xor     eax, eax
0x140826d56  mov     [rdx], rax
0x140826d59  mov     [rdx+8], eax
0x140826d5c  cmp     cs:g_ExpandCallback, rbx
0x140826d63  jnz     short loc_140826D88
0x140826d65  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x140826d6c  mov     r8d, 0AFh
0x140826d72  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140826d79  mov     ecx, 1
0x140826d7e  call    AslLogCallPrintf
0x140826d83  jmp     loc_140826E64
0x140826d88  mov     r14, [rcx]
0x140826d8b  cmp     dword ptr [r14+14h], 14h
0x140826d90  jnb     short loc_140826DA1
0x140826d92  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x140826d99  mov     r8d, 0B4h
0x140826d9f  jmp     short loc_140826D72
0x140826da1  mov     rcx, [r14+8]
0x140826da5  cmp     dword ptr [rcx+8], 6662647Ah
0x140826dac  jz      short loc_140826DBD
0x140826dae  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x140826db5  mov     r8d, 0BBh
0x140826dbb  jmp     short loc_140826D72
0x140826dbd  mov     eax, cs:g_ExpectedAlgorithm
0x140826dc3  cmp     [rcx+0Ch], eax
0x140826dc6  jz      short loc_140826DD7
0x140826dc8  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x140826dcf  mov     r8d, 0C0h
0x140826dd5  jmp     short loc_140826D72
0x140826dd7  mov     eax, [rcx+10h]
0x140826dda  mov     edx, eax
0x140826ddc  mov     [rsp+58h+arg_0], eax
0x140826de0  call    AslAlloc
0x140826de5  mov     rsi, rax
0x140826de8  test    rax, rax
0x140826deb  jnz     short loc_140826DFF
0x140826ded  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x140826df4  mov     r8d, 0D3h
0x140826dfa  jmp     loc_140826D72
0x140826dff  mov     r9d, [r14+14h]
0x140826e03  lea     rdx, [rsp+58h+arg_0]
0x140826e08  mov     r8, [r14+8]
0x140826e0c  sub     r9d, 14h
0x140826e10  mov     rax, cs:g_ExpandCallback
0x140826e17  add     r8, 14h
0x140826e1b  mov     rcx, rsi
0x140826e1e  call    _guard_dispatch_icall_no_overrides
0x140826e23  test    eax, eax
0x140826e25  jnz     short loc_140826E89
0x140826e27  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x140826e2e  mov     r8d, 0DDh
0x140826e34  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140826e3b  mov     ecx, 1
0x140826e40  call    AslLogCallPrintf
0x140826e45  mov     rdx, rsi
0x140826e48  call    AslFree
0x140826e4d  mov     [rsp+58h+arg_0], ebp
0x140826e51  test    rbx, rbx
0x140826e54  jz      short loc_140826E64
0x140826e56  mov     rcx, rbx
0x140826e59  mov     [rbx+8], rbp
0x140826e5d  call    SdbCloseDatabaseRead
0x140826e62  xor     ebx, ebx
0x140826e64  mov     rcx, [r15]
0x140826e67  call    SdbCloseDatabaseRead
0x140826e6c  mov     eax, ebp
0x140826e6e  mov     [r15], rbx
0x140826e71  mov     rbp, [rsp+58h+arg_10]
0x140826e76  mov     rbx, [rsp+58h+arg_8]
0x140826e7b  add     rsp, 30h
0x140826e7f  pop     r15
0x140826e81  pop     r14
0x140826e83  pop     r12
0x140826e85  pop     rdi
0x140826e86  pop     rsi
0x140826e87  retn
0x140826e89  mov     edx, [rsp+58h+arg_0]
0x140826e8d  mov     r8d, r12d
0x140826e90  mov     rcx, rsi
0x140826e93  call    SdbpOpenDatabaseInMemory
0x140826e98  mov     rbx, rax
0x140826e9b  test    rax, rax
0x140826e9e  jz      short loc_140826E45
0x140826ea0  or      dword ptr [rax+18h], 4
0x140826ea4  test    rdi, rdi
0x140826ea7  jz      short loc_140826ED2
0x140826ea9  mov     r9d, 0Ch
0x140826eaf  mov     r8, rdi
0x140826eb2  xor     edx, edx
0x140826eb4  mov     rcx, rax
0x140826eb7  call    SdbpReadMappedData
0x140826ebc  test    eax, eax
0x140826ebe  jnz     short loc_140826ED2
0x140826ec0  lea     r9, aFailedToReadEx; "Failed to read expanded database header"
0x140826ec7  mov     r8d, 0EEh
0x140826ecd  jmp     loc_140826E34
0x140826ed2  or      dword ptr [rbx+18h], 8
0x140826ed6  mov     ebp, 1
0x140826edb  mov     [rsp+58h+arg_0], 0
0x140826ee3  jmp     loc_140826E64
```
