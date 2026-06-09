# wil::details::in1diag3::Win32_Return_GetLastError(void *,uint,char const *)

- ea: `0x140002f5c`
- end: `0x140002f8f`
- name: `?Win32_Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `51`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002fa8`

## callees

- `0x140001dd4`
- `0x140002f5c`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Win32_Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int LastError; // eax
  unsigned int v5; // ecx
  int v7; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  LastError = wil::details::ReportFailure_GetLastErrorHr<1>(
                (__int64)this,
                (unsigned int)a2,
                a3,
                (__int64)a4,
                v7,
                retaddr);
  v5 = LastError;
  if ( LastError < 0 )
  {
    if ( (LastError & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)LastError;
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140002f5c  sub     rsp, 38h
0x140002f60  mov     rax, [rsp+38h]
0x140002f65  mov     [rsp+38h+var_10], rax
0x140002f6a  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140002f6f  mov     ecx, eax
0x140002f71  test    eax, eax
0x140002f73  js      short loc_140002F79
0x140002f75  xor     ecx, ecx
0x140002f77  jmp     short loc_140002F88
0x140002f79  and     eax, 1FFF0000h
0x140002f7e  cmp     eax, 70000h
0x140002f83  jnz     short loc_140002F88
0x140002f85  movzx   ecx, cx
0x140002f88  mov     eax, ecx
0x140002f8a  add     rsp, 38h
0x140002f8e  retn
```
