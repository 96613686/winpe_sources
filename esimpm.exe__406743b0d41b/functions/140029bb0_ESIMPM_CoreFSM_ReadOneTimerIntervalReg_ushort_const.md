# ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)

- ea: `0x140029bb0`
- end: `0x140029c49`
- name: `?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z`
- size: `153`
- prototype: `unsigned int(ESIMPM::CoreFSM *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140024220`

## callees

- `0x140014f64`
- `0x140020620`
- `0x1400282f4`
- `0x140029bb0`

## string_xrefs

- `0x140029c00`: `Reg value %s is not configured in registry`
- `0x140029bf4`: `ESIMPM::CoreFSM::ReadOneTimerIntervalReg`
- `0x140029c12`: `Failed to read reg value %s (error 0x%x)`

## pseudocode

```c
__int64 __fastcall ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ESIMPM::CoreFSM *this, const unsigned __int16 *a2)
{
  unsigned int DWORD; // eax
  struct _GUID *v5; // rdx
  unsigned int v7; // [rsp+20h] [rbp-18h]
  unsigned int v8; // [rsp+20h] [rbp-18h]
  unsigned int v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  DWORD = StateSeparation::GetDWORD(
            *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
            L"TimerIntervals",
            a2,
            &v9);
  v5 = (struct _GUID *)((char *)this + 184);
  if ( DWORD == 2 )
  {
    ESIMPM::Log::Info("ESIMPM::CoreFSM::ReadOneTimerIntervalReg", v5, L"Reg value %s is not configured in registry", a2);
    return 0;
  }
  if ( DWORD )
  {
    v7 = DWORD;
    ESIMPM::Log::Error(
      "ESIMPM::CoreFSM::ReadOneTimerIntervalReg",
      (wchar_t *)v5,
      L"Failed to read reg value %s (error 0x%x)",
      a2,
      v7);
    return 0;
  }
  v8 = v9;
  ESIMPM::Log::Info("ESIMPM::CoreFSM::ReadOneTimerIntervalReg", v5, L"Reg %s contains %d", a2, v8);
  return v9;
}

```

## disassembly

```asm
0x140029bb0  mov     [rsp+arg_0], rbx
0x140029bb5  push    rdi
0x140029bb6  sub     rsp, 30h
0x140029bba  mov     rbx, rcx
0x140029bbd  mov     [rsp+38h+arg_10], 0
0x140029bc5  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140029bcc  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x140029bd1  mov     rdi, rdx
0x140029bd4  mov     r8, rdx; unsigned __int16 *
0x140029bd7  lea     rdx, aTimerintervals; "TimerIntervals"
0x140029bde  mov     rcx, [rcx+3C0h]; this
0x140029be5  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x140029bea  lea     rdx, [rbx+0B8h]; struct _GUID *
0x140029bf1  mov     r9, rdi
0x140029bf4  lea     rcx, aEsimpmCorefsmR_0; "ESIMPM::CoreFSM::ReadOneTimerIntervalRe"...
0x140029bfb  cmp     eax, 2
0x140029bfe  jnz     short loc_140029C0E
0x140029c00  lea     r8, aRegValueSIsNot; "Reg value %s is not configured in regis"...
0x140029c07  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140029c0c  jmp     short loc_140029C22
0x140029c0e  test    eax, eax
0x140029c10  jz      short loc_140029C26
0x140029c12  lea     r8, aFailedToReadRe; "Failed to read reg value %s (error 0x%x"...
0x140029c19  mov     [rsp+38h+var_18], eax
0x140029c1d  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140029c22  xor     eax, eax
0x140029c24  jmp     short loc_140029C3E
0x140029c26  mov     eax, [rsp+38h+arg_10]
0x140029c2a  lea     r8, aRegSContainsD; "Reg %s contains %d"
0x140029c31  mov     [rsp+38h+var_18], eax
0x140029c35  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140029c3a  mov     eax, [rsp+38h+arg_10]
0x140029c3e  mov     rbx, [rsp+38h+arg_0]
0x140029c43  add     rsp, 30h
0x140029c47  pop     rdi
0x140029c48  retn
```
