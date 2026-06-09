# CLogFileCtrl::SetConfig(ulong,uchar *)

- ea: `0x180003000`
- end: `0x180003027`
- name: `?SetConfig@CLogFileCtrl@@UEAAJKPEAE@Z`
- size: `39`
- prototype: `__int64 __fastcall(CLogFileCtrl *this, __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003030`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::SetConfig(CLogFileCtrl *this, __int64 a2, unsigned __int8 *a3)
{
  *((_DWORD *)this + 26) = *((_DWORD *)a3 + 66);
  *((_DWORD *)this + 27) = *((_DWORD *)a3 + 67);
  CLogFileCtrl::SetLogFileDirectory(this, (const char *)a3 + 4);
  return 0;
}

```

## disassembly

```asm
0x180003000  sub     rsp, 28h
0x180003004  lea     rdx, [r8+4]; char *
0x180003008  mov     eax, [rdx+104h]
0x18000300e  mov     [rcx+68h], eax
0x180003011  mov     eax, [r8+10Ch]
0x180003018  mov     [rcx+6Ch], eax
0x18000301b  call    ?SetLogFileDirectory@CLogFileCtrl@@AEAAXPEBD@Z; CLogFileCtrl::SetLogFileDirectory(char const *)
0x180003020  xor     eax, eax
0x180003022  add     rsp, 28h
0x180003026  retn
```
