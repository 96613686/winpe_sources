# CMemoryTable::InternalPreUpdateStore(void)

- ea: `0x18000fb8c`
- end: `0x18000fc1e`
- name: `?InternalPreUpdateStore@CMemoryTable@@QEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(CMemoryTable *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180010c20`

## callees

- `0x18000f6bc`
- `0x18000fb8c`

## pseudocode

```c
__int64 __fastcall CMemoryTable::InternalPreUpdateStore(CMemoryTable *this)
{
  bool v1; // zf
  CMemoryTable *v2; // r10
  unsigned int v3; // r11d
  int RowFromIndex; // r8d
  int v5; // r11d
  __int64 i; // rdx
  __int64 result; // rax
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = (*((_BYTE *)this + 32) & 2) == 0;
  v2 = this;
  v8 = 0;
  if ( v1 || (*((_BYTE *)this + 92) & 4) == 0 )
    return 2147500033LL;
  v3 = 0;
LABEL_4:
  RowFromIndex = CMemoryTable::GetRowFromIndex(v2, 1u, v3, &v8);
  if ( RowFromIndex < 0 )
  {
    result = 0;
    if ( RowFromIndex != -2145318890 )
      return (unsigned int)RowFromIndex;
  }
  else
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *((_DWORD *)v2 + 9) )
      {
        v3 = v5 + 1;
        goto LABEL_4;
      }
      if ( (*(_DWORD *)(*((_QWORD *)v2 + 7) + 12 * i + 8) & 0x80000) != 0
        && (*((_BYTE *)v8 + *(unsigned __int16 *)(*((_QWORD *)v2 + 8) + 8 * i)) & 2) == 0 )
      {
        break;
      }
    }
    return 2149648416LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000fb8c  sub     rsp, 28h
0x18000fb90  test    byte ptr [rcx+20h], 2
0x18000fb94  mov     r10, rcx
0x18000fb97  mov     [rsp+28h+arg_0], 0
0x18000fba0  jz      short loc_18000FC14
0x18000fba2  test    byte ptr [rcx+5Ch], 4
0x18000fba6  jz      short loc_18000FC14
0x18000fba8  xor     r11d, r11d
0x18000fbab  lea     r9, [rsp+28h+arg_0]; void **
0x18000fbb0  mov     r8d, r11d; unsigned int
0x18000fbb3  mov     edx, 1; unsigned int
0x18000fbb8  mov     rcx, r10; this
0x18000fbbb  call    ?GetRowFromIndex@CMemoryTable@@AEAAJKKPEAPEAX@Z; CMemoryTable::GetRowFromIndex(ulong,ulong,void * *)
0x18000fbc0  mov     r8d, eax
0x18000fbc3  test    eax, eax
0x18000fbc5  js      short loc_18000FC05
0x18000fbc7  mov     r9, [rsp+28h+arg_0]
0x18000fbcc  xor     edx, edx
0x18000fbce  cmp     edx, [r10+24h]
0x18000fbd2  jnb     short loc_18000FBF9
0x18000fbd4  mov     rax, [r10+38h]
0x18000fbd8  lea     rcx, [rdx+rdx*2]
0x18000fbdc  test    dword ptr [rax+rcx*4+8], 80000h
0x18000fbe4  jz      short loc_18000FBF5
0x18000fbe6  mov     rax, [r10+40h]
0x18000fbea  movzx   ecx, word ptr [rax+rdx*8]
0x18000fbee  test    byte ptr [rcx+r9], 2
0x18000fbf3  jz      short loc_18000FBFE
0x18000fbf5  inc     edx
0x18000fbf7  jmp     short loc_18000FBCE
0x18000fbf9  inc     r11d
0x18000fbfc  jmp     short loc_18000FBAB
0x18000fbfe  mov     eax, 80210820h
0x18000fc03  jmp     short loc_18000FC19
0x18000fc05  xor     eax, eax
0x18000fc07  cmp     r8d, 80210816h
0x18000fc0e  cmovnz  eax, r8d
0x18000fc12  jmp     short loc_18000FC19
0x18000fc14  mov     eax, 80004001h
0x18000fc19  add     rsp, 28h
0x18000fc1d  retn
```
