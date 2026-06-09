# HbEvtpGetLogConfiguration

- ea: `0x140001230`
- end: `0x140001268`
- name: `HbEvtpGetLogConfiguration`
- size: `56`
- prototype: `__int64 __fastcall(int, __int64 **)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001900`
- `0x140001d60`
- `0x140010a78`
- `0x140010c0c`
- `0x140011420`
- `0x140011760`
- `0x1400137b0`
- `0x14001396c`
- `0x140013ef0`
- `0x140014810`
- `0x140014bf0`

## callees

- `0x140001230`

## pseudocode

```c
__int64 __fastcall HbEvtpGetLogConfiguration(int a1, __int64 **a2)
{
  __int64 *v2; // rax
  int v4; // ecx

  if ( !a1 )
  {
    v2 = HbEvtpEventLog;
LABEL_3:
    *a2 = v2;
    return 0;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v2 = qword_140009360;
    goto LABEL_3;
  }
  if ( v4 == 1 )
  {
    *a2 = (__int64 *)&dword_1400093F0;
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140001230  test    ecx, ecx
0x140001232  jnz     short loc_140001242
0x140001234  lea     rax, HbEvtpEventLog
0x14000123b  mov     [rdx], rax
0x14000123e  xor     eax, eax
0x140001240  retn
0x140001242  sub     ecx, 1
0x140001245  jz      short loc_14000125F
0x140001247  cmp     ecx, 1
0x14000124a  jz      short loc_140001253
0x14000124c  mov     eax, 0C000000Dh
0x140001251  retn
0x140001253  lea     rcx, dword_1400093F0
0x14000125a  mov     [rdx], rcx
0x14000125d  jmp     short loc_14000123E
0x14000125f  lea     rax, qword_140009360
0x140001266  jmp     short loc_14000123B
```
