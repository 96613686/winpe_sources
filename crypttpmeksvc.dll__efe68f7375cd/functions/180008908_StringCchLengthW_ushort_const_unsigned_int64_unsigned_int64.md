# StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180008908`
- end: `0x18000893b`
- name: `?StringCchLengthW@@YAJPEBG_KPEA_K@Z`
- size: `51`
- prototype: `HRESULT __fastcall(const unsigned __int16 *, size_t, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d58`
- `0x18000a1c8`

## callees

- `0x180008908`
- `0x180008944`

## pseudocode

```c
HRESULT __fastcall StringCchLengthW(const unsigned __int16 *a1, size_t a2, unsigned __int64 *a3)
{
  HRESULT result; // eax

  if ( a1 && a2 <= 0x7FFFFFFF )
  {
    result = StringLengthWorkerW(a1, a2, a3);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( a3 )
    *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180008908  sub     rsp, 28h
0x18000890c  test    rcx, rcx
0x18000890f  jz      short loc_180008925
0x180008911  cmp     rdx, 7FFFFFFFh
0x180008918  ja      short loc_180008925
0x18000891a  call    StringLengthWorkerW
0x18000891f  test    eax, eax
0x180008921  jns     short loc_180008936
0x180008923  jmp     short loc_18000892A
0x180008925  mov     eax, 80070057h
0x18000892a  test    r8, r8
0x18000892d  jz      short loc_180008936
0x18000892f  mov     qword ptr [r8], 0
0x180008936  add     rsp, 28h
0x18000893a  retn
```
