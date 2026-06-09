# CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)

- ea: `0x18000e534`
- end: `0x18000e74a`
- name: `?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z`
- size: `534`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e160`
- `0x1800103a0`
- `0x18001195c`
- `0x180012e18`
- `0x180013178`
- `0x180014328`

## callees

- `0x18000e424`
- `0x18000e534`
- `0x18000e750`
- `0x18000fa24`
- `0x18001031c`
- `0x180011330`
- `0x180014bdc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000e5fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e626`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e721`
- `ntdll!RtlLeaveCriticalSection` at `0x18001571d`
- `ntdll!RtlLeaveCriticalSection` at `0x180015741`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e5fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e626`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e721`
- `ntdll!RtlLeaveCriticalSection` at `0x18001571d`
- `ntdll!RtlLeaveCriticalSection` at `0x180015741`
- `ntdll!RtlEnterCriticalSection` at `0x18000e579`
- `ntdll!RtlEnterCriticalSection` at `0x18000e5b9`
- `ntdll!RtlEnterCriticalSection` at `0x18000e579`
- `ntdll!RtlEnterCriticalSection` at `0x18000e5b9`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::AllocateIocb(__int64 a1, int a2, struct CLogIocb **a3)
{
  unsigned int IocbNaked; // edi
  volatile signed __int32 *v7; // rbx
  unsigned __int32 v8; // esi
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  int v10; // r8d
  struct _RTL_CRITICAL_SECTION *CriticalSection; // [rsp+A8h] [rbp+20h]

  IocbNaked = 0;
  CriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 288));
  if ( a2 != 1 )
  {
    v7 = (volatile signed __int32 *)(a1 + 112);
    v8 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
    if ( v8 > *(_DWORD *)(a1 + 120) )
    {
      _InterlockedDecrement(v7);
      goto LABEL_7;
    }
LABEL_9:
    IocbNaked = CClfsMarshallingContext::AllocateIocbNaked((CClfsMarshallingContext *)a1, a3);
    if ( !IocbNaked && *a3 )
    {
      *((_DWORD *)*a3 + 4) = -(a2 != 1) - 1040322544;
      *((_DWORD *)*a3 + 5) = 224;
      IocbNaked = CLogIocb::AllocateBuffer(*a3, *(_DWORD *)(a1 + 128));
      if ( !IocbNaked )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        {
          WPP_SF_slqqdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            v10,
            (unsigned int)"CClfsMarshallingContext::AllocateIocb",
            80,
            a1,
            (char)*a3,
            v8,
            *(_DWORD *)(a1 + 140));
        }
        goto LABEL_19;
      }
      CClfsMarshallingContext::FreeIocbNaked((CClfsMarshallingContext *)a1, *a3);
      *a3 = 0;
    }
    _InterlockedDecrement(v7);
    goto LABEL_19;
  }
  v7 = (volatile signed __int32 *)(a1 + 116);
  v8 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 116));
  if ( v8 <= *(_DWORD *)(a1 + 124) )
    goto LABEL_9;
  _InterlockedDecrement(v7);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 328));
  if ( !(unsigned int)CFlushQ::IsEmpty((CFlushQ *)(a1 + 232)) )
    IocbNaked = CClfsMarshallingContext::Flush((CClfsMarshallingContext *)a1);
  v8 = _InterlockedIncrement(v7);
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 328);
  if ( v8 <= *(_DWORD *)(a1 + 124) )
  {
    RtlLeaveCriticalSection(v9);
    goto LABEL_9;
  }
  RtlLeaveCriticalSection(v9);
  _InterlockedDecrement(v7);
  if ( !IocbNaked )
LABEL_7:
    IocbNaked = 6605;
LABEL_19:
  RtlLeaveCriticalSection(CriticalSection);
  return IocbNaked;
}

```

## disassembly

```asm
0x18000e534  mov     rax, rsp
0x18000e537  mov     [rax+10h], rbx
0x18000e53b  mov     [rax+18h], rsi
0x18000e53f  mov     [rax+8], rcx
0x18000e543  push    rdi
0x18000e544  push    r12
0x18000e546  push    r13
0x18000e548  push    r14
0x18000e54a  push    r15
0x18000e54c  sub     rsp, 60h
0x18000e550  mov     r15, r8
0x18000e553  mov     r12d, edx
0x18000e556  mov     r14, rcx
0x18000e559  xor     r13d, r13d
0x18000e55c  mov     edi, r13d
0x18000e55f  mov     [rax-38h], r13b
0x18000e563  mov     [rax-37h], r13b
0x18000e567  lea     rax, [rcx+120h]
0x18000e56e  mov     [rsp+88h+CriticalSection], rax
0x18000e576  mov     rcx, rax; CriticalSection
0x18000e579  call    cs:__imp_RtlEnterCriticalSection
0x18000e580  nop     dword ptr [rax+rax+00h]
0x18000e585  lea     eax, [r13+1]
0x18000e589  mov     [rsp+88h+var_37], al
0x18000e58d  mov     esi, eax
0x18000e58f  cmp     r12d, eax
0x18000e592  jnz     loc_18000E6A2
0x18000e598  lea     rbx, [r14+74h]
0x18000e59c  lock xadd [rbx], esi
0x18000e5a0  add     esi, eax
0x18000e5a2  cmp     esi, [r14+7Ch]
0x18000e5a6  jbe     loc_18000E63A
0x18000e5ac  lock dec dword ptr [rbx]
0x18000e5af  lea     r13, [r14+148h]
0x18000e5b6  mov     rcx, r13; CriticalSection
0x18000e5b9  call    cs:__imp_RtlEnterCriticalSection
0x18000e5c0  nop     dword ptr [rax+rax+00h]
0x18000e5c5  mov     [rsp+88h+var_38], 1
0x18000e5ca  lea     rcx, [r14+0E8h]; this
0x18000e5d1  call    ?IsEmpty@CFlushQ@@QEAAHXZ; CFlushQ::IsEmpty(void)
0x18000e5d6  test    eax, eax
0x18000e5d8  jnz     short loc_18000E5E8
0x18000e5da  mov     rcx, r14; this
0x18000e5dd  call    ?Flush@CClfsMarshallingContext@@AEAAKXZ; CClfsMarshallingContext::Flush(void)
0x18000e5e2  mov     edi, eax
0x18000e5e4  mov     [rsp+88h+var_34], eax
0x18000e5e8  mov     esi, 1
0x18000e5ed  lock xadd [rbx], esi
0x18000e5f1  inc     esi
0x18000e5f3  mov     rcx, r13; CriticalSection
0x18000e5f6  cmp     esi, [r14+7Ch]
0x18000e5fa  jbe     short loc_18000E626
0x18000e5fc  call    cs:__imp_RtlLeaveCriticalSection
0x18000e603  nop     dword ptr [rax+rax+00h]
0x18000e608  mov     [rsp+88h+var_38], 0
0x18000e60d  lock dec dword ptr [rbx]
0x18000e610  test    edi, edi
0x18000e612  jnz     loc_18000E719
0x18000e618  mov     edi, 19CDh
0x18000e61d  mov     [rsp+88h+var_34], edi
0x18000e621  jmp     loc_18000E719
0x18000e626  call    cs:__imp_RtlLeaveCriticalSection
0x18000e62d  nop     dword ptr [rax+rax+00h]
0x18000e632  xor     r13d, r13d
0x18000e635  mov     [rsp+88h+var_38], r13b
0x18000e63a  mov     rdx, r15; struct CLogIocb **
0x18000e63d  mov     rcx, r14; this
0x18000e640  call    ?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)
0x18000e645  mov     edi, eax
0x18000e647  mov     [rsp+88h+var_34], eax
0x18000e64b  test    eax, eax
0x18000e64d  jnz     loc_18000E711
0x18000e653  mov     rcx, [r15]
0x18000e656  test    rcx, rcx
0x18000e659  jz      loc_18000E711
0x18000e65f  dec     r12d
0x18000e662  neg     r12d
0x18000e665  sbb     eax, eax
0x18000e667  add     eax, 0C1FDF010h
0x18000e66c  mov     [rcx+10h], eax
0x18000e66f  mov     rax, [r15]
0x18000e672  mov     dword ptr [rax+14h], 0E0h
0x18000e679  mov     edx, [r14+80h]; unsigned int
0x18000e680  mov     rcx, [r15]; this
0x18000e683  call    ?AllocateBuffer@CLogIocb@@QEAAKK@Z; CLogIocb::AllocateBuffer(ulong)
0x18000e688  mov     edi, eax
0x18000e68a  mov     [rsp+88h+var_34], eax
0x18000e68e  test    eax, eax
0x18000e690  jz      short loc_18000E6BA
0x18000e692  mov     rdx, [r15]; struct CLogIocb *
0x18000e695  mov     rcx, r14; this
0x18000e698  call    ?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)
0x18000e69d  mov     [r15], r13
0x18000e6a0  jmp     short loc_18000E711
0x18000e6a2  lea     rbx, [r14+70h]
0x18000e6a6  lock xadd [rbx], esi
0x18000e6aa  add     esi, eax
0x18000e6ac  cmp     esi, [r14+78h]
0x18000e6b0  jbe     short loc_18000E63A
0x18000e6b2  lock dec dword ptr [rbx]
0x18000e6b5  jmp     loc_18000E618
0x18000e6ba  lea     rax, WPP_GLOBAL_Control
0x18000e6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6c8  cmp     rcx, rax
0x18000e6cb  jz      short loc_18000E714
0x18000e6cd  test    dword ptr [rcx+1Ch], 4000000h
0x18000e6d4  jz      short loc_18000E714
0x18000e6d6  mov     edx, 0Bh
0x18000e6db  mov     eax, [r14+8Ch]
0x18000e6e2  mov     [rsp+88h+var_48], eax
0x18000e6e6  mov     [rsp+88h+var_50], esi
0x18000e6ea  mov     rax, [r15]
0x18000e6ed  mov     [rsp+88h+var_58], rax
0x18000e6f2  mov     [rsp+88h+var_60], r14
0x18000e6f7  mov     [rsp+88h+var_68], 1550h
0x18000e6ff  lea     r9, aCclfsmarshalli; "CClfsMarshallingContext::AllocateIocb"
0x18000e706  mov     rcx, [rcx+10h]
0x18000e70a  call    WPP_SF_slqqdd
0x18000e70f  jmp     short loc_18000E714
0x18000e711  lock dec dword ptr [rbx]
0x18000e714  mov     [rsp+88h+var_38], r13b
0x18000e719  mov     rcx, [rsp+88h+CriticalSection]; CriticalSection
0x18000e721  call    cs:__imp_RtlLeaveCriticalSection
0x18000e728  nop     dword ptr [rax+rax+00h]
0x18000e72d  mov     eax, edi
0x18000e72f  lea     r11, [rsp+88h+var_28]
0x18000e734  mov     rbx, [r11+38h]
0x18000e738  mov     rsi, [r11+40h]
0x18000e73c  mov     rsp, r11
0x18000e73f  pop     r15
0x18000e741  pop     r14
0x18000e743  pop     r13
0x18000e745  pop     r12
0x18000e747  pop     rdi
0x18000e748  retn
0x180015700  push    rbp
0x180015702  sub     rsp, 50h
0x180015706  mov     rbp, rdx
0x180015709  cmp     byte ptr [rbp+51h], 0
0x18001570d  jz      short loc_18001572D
0x18001570f  mov     rcx, [rbp+90h]
0x180015716  add     rcx, 120h; CriticalSection
0x18001571d  call    cs:__imp_RtlLeaveCriticalSection
0x180015724  nop     dword ptr [rax+rax+00h]
0x180015729  mov     byte ptr [rbp+51h], 0
0x18001572d  cmp     byte ptr [rbp+50h], 0
0x180015731  jz      short loc_180015751
0x180015733  mov     rcx, [rbp+90h]
0x18001573a  add     rcx, 148h; CriticalSection
0x180015741  call    cs:__imp_RtlLeaveCriticalSection
0x180015748  nop     dword ptr [rax+rax+00h]
0x18001574d  mov     byte ptr [rbp+50h], 0
0x180015751  add     rsp, 50h
0x180015755  pop     rbp
0x180015756  retn
```
