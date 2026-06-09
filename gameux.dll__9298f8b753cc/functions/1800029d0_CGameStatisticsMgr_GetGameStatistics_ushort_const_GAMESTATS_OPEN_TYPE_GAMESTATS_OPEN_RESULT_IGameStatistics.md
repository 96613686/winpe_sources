# CGameStatisticsMgr::GetGameStatistics(ushort const *,GAMESTATS_OPEN_TYPE,GAMESTATS_OPEN_RESULT *,IGameStatistics * *)

- ea: `0x1800029d0`
- end: `0x1800029ed`
- name: `?GetGameStatistics@CGameStatisticsMgr@@UEAAJPEBGW4GAMESTATS_OPEN_TYPE@@PEAW4GAMESTATS_OPEN_RESULT@@PEAPEAUIGameStatistics@@@Z`
- size: `29`
- prototype: `int(CGameStatisticsMgr *__hidden this, const unsigned __int16 *, enum GAMESTATS_OPEN_TYPE, enum GAMESTATS_OPEN_RESULT *, struct IGameStatistics **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002788`
- `0x1800029d0`

## pseudocode

```c
__int64 __fastcall CGameStatisticsMgr::GetGameStatistics(
        CGameStatisticsMgr *this,
        const unsigned __int16 *a2,
        enum GAMESTATS_OPEN_TYPE a3,
        enum GAMESTATS_OPEN_RESULT *a4,
        struct IGameStatistics **a5)
{
  if ( a2 && a5 )
    return CGameStatistics::Create(a4, a5);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x1800029d0  test    rdx, rdx
0x1800029d3  jz      short loc_1800029E7
0x1800029d5  mov     rdx, [rsp+arg_20]; struct IGameStatistics **
0x1800029da  test    rdx, rdx
0x1800029dd  jz      short loc_1800029E7
0x1800029df  mov     rcx, r9; enum GAMESTATS_OPEN_RESULT *
0x1800029e2  jmp     ?Create@CGameStatistics@@SAJPEAW4GAMESTATS_OPEN_RESULT@@PEAPEAUIGameStatistics@@@Z; CGameStatistics::Create(GAMESTATS_OPEN_RESULT *,IGameStatistics * *)
0x1800029e7  mov     eax, 80070057h
0x1800029ec  retn
```
