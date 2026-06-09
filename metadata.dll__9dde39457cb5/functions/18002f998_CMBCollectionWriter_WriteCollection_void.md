# CMBCollectionWriter::WriteCollection(void)

- ea: `0x18002f998`
- end: `0x18002fa21`
- name: `?WriteCollection@CMBCollectionWriter@@QEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(CMBCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800120b4`

## callees

- `0x180006d08`
- `0x18002f494`
- `0x18002f998`
- `0x18003059c`
- `0x180030634`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f9d7`
- `msvcrt!_wcsicmp` at `0x18002f9d7`

## string_xrefs

- `0x18002f9cc`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall CMBCollectionWriter::WriteCollection(CMBCollectionWriter *this)
{
  __int64 result; // rax
  __int64 i; // rbx
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // r9d

  result = CMBCollectionWriter::BeginWriteCollection(this);
  if ( (int)result >= 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); i = (unsigned int)(i + 1) )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * i);
      if ( *(_DWORD *)(v4 + 56) )
      {
        result = _wcsicmp(*(const wchar_t **)(*(_QWORD *)(v4 + 64) + 8LL), L"IIsConfigObject")
               ? CMBPropertyWriter::WritePropertyShort((CMBPropertyWriter *)v4, v5, v6, v7)
               : CMBPropertyWriter::WritePropertyLong((CMBPropertyWriter *)v4);
        if ( (int)result < 0 )
          return result;
      }
    }
    return CWriter::WriteToFile(*(CWriter **)this, L"\t\t</Collection>\r\n", g_cchEndCollection, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002f998  mov     [rsp+arg_0], rbx
0x18002f99d  mov     [rsp+arg_8], rsi
0x18002f9a2  push    rdi
0x18002f9a3  sub     rsp, 20h
0x18002f9a7  mov     rdi, rcx
0x18002f9aa  call    ?BeginWriteCollection@CMBCollectionWriter@@AEAAJXZ; CMBCollectionWriter::BeginWriteCollection(void)
0x18002f9af  test    eax, eax
0x18002f9b1  js      short loc_18002FA11
0x18002f9b3  xor     ebx, ebx
0x18002f9b5  cmp     ebx, [rdi+2Ch]
0x18002f9b8  jnb     short loc_18002F9F8
0x18002f9ba  mov     rax, [rdi+20h]
0x18002f9be  mov     rsi, [rax+rbx*8]
0x18002f9c2  cmp     dword ptr [rsi+38h], 0
0x18002f9c6  jz      short loc_18002F9F4
0x18002f9c8  mov     rcx, [rsi+40h]
0x18002f9cc  lea     rdx, aIisconfigobjec; "IIsConfigObject"
0x18002f9d3  mov     rcx, [rcx+8]; String1
0x18002f9d7  call    cs:__imp__wcsicmp
0x18002f9dd  mov     rcx, rsi; this
0x18002f9e0  test    eax, eax
0x18002f9e2  jnz     short loc_18002F9EB
0x18002f9e4  call    ?WritePropertyLong@CMBPropertyWriter@@AEAAJXZ; CMBPropertyWriter::WritePropertyLong(void)
0x18002f9e9  jmp     short loc_18002F9F0
0x18002f9eb  call    ?WritePropertyShort@CMBPropertyWriter@@AEAAJXZ; CMBPropertyWriter::WritePropertyShort(void)
0x18002f9f0  test    eax, eax
0x18002f9f2  js      short loc_18002FA11
0x18002f9f4  inc     ebx
0x18002f9f6  jmp     short loc_18002F9B5
0x18002f9f8  mov     r8d, cs:?g_cchEndCollection@@3KA; unsigned int
0x18002f9ff  lea     rdx, aCollection; "\t\t</Collection>\r\n"
0x18002fa06  mov     rcx, [rdi]; this
0x18002fa09  xor     r9d, r9d; int
0x18002fa0c  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002fa11  mov     rbx, [rsp+28h+arg_0]
0x18002fa16  mov     rsi, [rsp+28h+arg_8]
0x18002fa1b  add     rsp, 20h
0x18002fa1f  pop     rdi
0x18002fa20  retn
```
