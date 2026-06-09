# StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x140008808`
- end: `0x140008837`
- name: `?StringCchLengthW@@YAJPEBG_KPEA_K@Z`
- size: `47`
- prototype: `HRESULT __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011e4`
- `0x1400040d4`

## callees

- `0x140008808`
- `0x1400089a4`

## pseudocode

```c
HRESULT __fastcall StringCchLengthW(const unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  HRESULT result; // eax

  if ( a1 )
  {
    result = StringLengthWorkerW(a1, 0x7FFFFFFFu, a3);
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
0x140008808  sub     rsp, 28h
0x14000880c  test    rcx, rcx
0x14000880f  jz      short loc_140008821
0x140008811  mov     edx, 7FFFFFFFh; cchMax
0x140008816  call    StringLengthWorkerW
0x14000881b  test    eax, eax
0x14000881d  jns     short loc_140008832
0x14000881f  jmp     short loc_140008826
0x140008821  mov     eax, 80070057h
0x140008826  test    r8, r8
0x140008829  jz      short loc_140008832
0x14000882b  mov     qword ptr [r8], 0
0x140008832  add     rsp, 28h
0x140008836  retn
```
