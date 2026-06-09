# SmbCeUpdateExchangeStatus

- ea: `0x14001c040`
- end: `0x14001c06b`
- name: `SmbCeUpdateExchangeStatus`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001b2d0`
- `0x140021ee0`
- `0x140028500`
- `0x140033a30`

## callees

- `0x14001c040`

## import_xrefs

- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001c05d`
- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001c05d`

## pseudocode

```c
__int64 __fastcall SmbCeUpdateExchangeStatus(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 259 )
    {
      _InterlockedExchange64((volatile __int64 *)(a1 + 16), a2);
      return SmbCeUpdateExchangeHistory(a1, a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001c040  sub     rsp, 28h
0x14001c044  test    edx, edx
0x14001c046  jnz     short loc_14001C04E
0x14001c048  add     rsp, 28h
0x14001c04c  retn
0x14001c04e  cmp     edx, 103h
0x14001c054  jz      short loc_14001C048
0x14001c056  mov     rax, rdx
0x14001c059  xchg    rax, [rcx+10h]
0x14001c05d  call    cs:__imp_SmbCeUpdateExchangeHistory
0x14001c064  nop     dword ptr [rax+rax+00h]
0x14001c069  jmp     short loc_14001C048
```
