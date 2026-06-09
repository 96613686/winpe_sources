# KsecIoctlCopyPool(void *,ulong)

- ea: `0x18000d2f0`
- end: `0x18000d56c`
- name: `?KsecIoctlCopyPool@@YAJPEAXK@Z`
- size: `636`
- prototype: `__int64 __fastcall(void *Src, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180007a64`
- `0x18000d2f0`
- `0x18000dad4`
- `0x18000dd48`
- `0x18000dde0`
- `0x18000df18`
- `0x18000df74`
- `0x18001f520`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d354`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d354`
- `ntoskrnl!ProbeForRead` at `0x18000d37c`
- `ntoskrnl!ProbeForRead` at `0x18000d37c`

## pseudocode

```c
__int64 __fastcall KsecIoctlCopyPool(void *Src, int a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int128 v8; // kr00_16
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rdi
  unsigned __int128 Address; // [rsp+60h] [rbp-28h] BYREF
  __int128 Length; // [rsp+70h] [rbp-18h]
  __int64 v15; // [rsp+90h] [rbp+8h] BYREF

  Address = 0;
  Length = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
  if ( Src && (v4 = 32, a2 == 32) )
  {
    if ( v15 )
    {
      if ( ((unsigned __int8)Src & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&Address, Src, 0x20u);
      ProbeForRead((volatile void *)Address, (unsigned int)Length, 1u);
      if ( (unsigned int)KsecValidateAddress(*((void **)&Address + 1), Length, SDWORD1(Length)) )
      {
        if ( DWORD1(Length) )
        {
          v8 = Address;
          RtlCopyFromUser(*((void **)&Address + 1), (void *)Address, (unsigned int)Length);
        }
        else
        {
          v11 = *((_QWORD *)&Address + 1);
          v12 = Address;
          RtlCopyToUser((void *)Address, *((void **)&Address + 1), (unsigned int)Length);
          v8 = __PAIR128__(v12, v11);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
          WPP_SF_dLqqL(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v9,
            v10,
            DWORD2(Length),
            DWORD1(Length),
            *((_QWORD *)&v8 + 1),
            v8,
            Length);
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_qLL(*((_QWORD *)WPP_GLOBAL_Control + 3), v5, v6, *((_QWORD *)&Address + 1), Length, DWORD2(Length));
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
        return 3221225506LL;
      }
    }
    else
    {
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
      return 3221226238LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 18, v4, Src, a2);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d2f0  mov     rax, rsp
0x18000d2f3  mov     [rax+10h], rbx
0x18000d2f7  mov     [rax+18h], rsi
0x18000d2fb  push    rdi
0x18000d2fc  sub     rsp, 80h
0x18000d303  mov     edi, edx
0x18000d305  mov     rbx, rcx
0x18000d308  xorps   xmm0, xmm0
0x18000d30b  movups  xmmword ptr [rax-28h], xmm0
0x18000d30f  movups  xmmword ptr [rax-18h], xmm0
0x18000d313  lea     rcx, [rax+8]; this
0x18000d317  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000d31c  test    rbx, rbx
0x18000d31f  jz      loc_18000D515
0x18000d325  mov     r8d, 20h ; ' '
0x18000d32b  cmp     edi, r8d
0x18000d32e  jnz     loc_18000D515
0x18000d334  cmp     [rsp+88h+arg_0], 0
0x18000d33d  jz      loc_18000D501
0x18000d343  xor     esi, esi
0x18000d345  mov     [rsp+88h+var_38], rsi
0x18000d34a  mov     [rsp+88h+var_30], rsi
0x18000d34f  test    bl, 7
0x18000d352  jz      short loc_18000D360
0x18000d354  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000d35b  nop     dword ptr [rax+rax+00h]
0x18000d360  mov     rdx, rbx; Src
0x18000d363  lea     rcx, [rsp+88h+Address]; void *
0x18000d368  call    RtlCopyFromUser
0x18000d36d  mov     edx, dword ptr [rsp+88h+Length]; Length
0x18000d371  mov     r8d, 1; Alignment
0x18000d377  mov     rcx, [rsp+88h+Address]; Address
0x18000d37c  call    cs:__imp_ProbeForRead
0x18000d383  nop     dword ptr [rax+rax+00h]
0x18000d388  nop
0x18000d389  mov     r8d, dword ptr [rsp+88h+Length+4]; int
0x18000d38e  mov     edx, dword ptr [rsp+88h+Length]; unsigned int
0x18000d392  mov     rcx, [rsp+88h+Src]; void *
0x18000d397  call    ?KsecValidateAddress@@YAHPEAXKH@Z; KsecValidateAddress(void *,ulong,int)
0x18000d39c  test    eax, eax
0x18000d39e  jnz     short loc_18000D3EF
0x18000d3a0  lea     rax, WPP_GLOBAL_Control
0x18000d3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3ae  cmp     rcx, rax
0x18000d3b1  jz      short loc_18000D3D8
0x18000d3b3  mov     eax, [rcx+2Ch]
0x18000d3b6  test    al, 1
0x18000d3b8  jz      short loc_18000D3D8
0x18000d3ba  mov     eax, [rsp+88h+var_10]
0x18000d3be  mov     dword ptr [rsp+88h+var_60], eax
0x18000d3c2  mov     eax, dword ptr [rsp+88h+Length]
0x18000d3c6  mov     [rsp+88h+var_68], eax
0x18000d3ca  mov     r9, [rsp+88h+Src]
0x18000d3cf  mov     rcx, [rcx+18h]
0x18000d3d3  call    WPP_SF_qLL
0x18000d3d8  lea     rcx, [rsp+88h+arg_0]; this
0x18000d3e0  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d3e5  mov     eax, 0C0000022h
0x18000d3ea  jmp     loc_18000D556
0x18000d3ef  cmp     dword ptr [rsp+88h+Length+4], 0
0x18000d3f4  jz      short loc_18000D41C
0x18000d3f6  mov     rbx, [rsp+88h+Address]
0x18000d3fb  mov     [rsp+88h+var_30], rbx
0x18000d400  mov     rdi, [rsp+88h+Src]
0x18000d405  mov     [rsp+88h+var_38], rdi
0x18000d40a  mov     r8d, dword ptr [rsp+88h+Length]; Size
0x18000d40f  mov     rdx, rbx; Src
0x18000d412  mov     rcx, rdi; void *
0x18000d415  call    RtlCopyFromUser
0x18000d41a  jmp     short loc_18000D440
0x18000d41c  mov     rbx, [rsp+88h+Src]
0x18000d421  mov     [rsp+88h+var_30], rbx
0x18000d426  mov     rdi, [rsp+88h+Address]
0x18000d42b  mov     [rsp+88h+var_38], rdi
0x18000d430  mov     r8d, dword ptr [rsp+88h+Length]; Size
0x18000d435  mov     rdx, rbx; Src
0x18000d438  mov     rcx, rdi; void *
0x18000d43b  call    RtlCopyToUser
0x18000d440  jmp     short loc_18000D44E
0x18000d442  mov     esi, eax
0x18000d444  mov     rdi, [rsp+88h+var_38]
0x18000d449  mov     rbx, [rsp+88h+var_30]
0x18000d44e  test    esi, esi
0x18000d450  js      short loc_18000D496
0x18000d452  lea     rax, WPP_GLOBAL_Control
0x18000d459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d460  cmp     rcx, rax
0x18000d463  jz      short loc_18000D4DC
0x18000d465  mov     eax, [rcx+2Ch]
0x18000d468  test    al, 10h
0x18000d46a  jz      short loc_18000D4DC
0x18000d46c  mov     eax, dword ptr [rsp+88h+Length]
0x18000d470  mov     dword ptr [rsp+88h+var_50], eax
0x18000d474  mov     [rsp+88h+var_58], rbx
0x18000d479  mov     [rsp+88h+var_60], rdi
0x18000d47e  mov     eax, dword ptr [rsp+88h+Length+4]
0x18000d482  mov     [rsp+88h+var_68], eax
0x18000d486  mov     r9d, [rsp+88h+var_10]
0x18000d48b  mov     rcx, [rcx+18h]
0x18000d48f  call    WPP_SF_dLqqL
0x18000d494  jmp     short loc_18000D4DC
0x18000d496  lea     rax, WPP_GLOBAL_Control
0x18000d49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4a4  cmp     rcx, rax
0x18000d4a7  jz      short loc_18000D4DC
0x18000d4a9  mov     eax, [rcx+2Ch]
0x18000d4ac  test    al, 1
0x18000d4ae  jz      short loc_18000D4DC
0x18000d4b0  mov     edx, dword ptr [rsp+88h+Length]
0x18000d4b4  mov     [rsp+88h+var_48], edx
0x18000d4b8  mov     [rsp+88h+var_50], rbx
0x18000d4bd  mov     [rsp+88h+var_58], rdi
0x18000d4c2  mov     dword ptr [rsp+88h+var_60], esi
0x18000d4c6  mov     edx, dword ptr [rsp+88h+Length+4]
0x18000d4ca  mov     [rsp+88h+var_68], edx
0x18000d4ce  mov     r9d, [rsp+88h+var_10]
0x18000d4d3  mov     rcx, [rcx+18h]
0x18000d4d7  call    WPP_SF_dLLqqL
0x18000d4dc  lea     rcx, [rsp+88h+arg_0]; this
0x18000d4e4  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d4e9  mov     eax, esi
0x18000d4eb  jmp     short loc_18000D556
0x18000d4ed  lea     rcx, [rsp+88h+arg_0]; this
0x18000d4f5  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d4fa  mov     eax, 0C0000005h
0x18000d4ff  jmp     short loc_18000D556
0x18000d501  lea     rcx, [rsp+88h+arg_0]; this
0x18000d509  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d50e  mov     eax, 0C00002FEh
0x18000d513  jmp     short loc_18000D556
0x18000d515  lea     rax, WPP_GLOBAL_Control
0x18000d51c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d523  cmp     rcx, rax
0x18000d526  jz      short loc_18000D544
0x18000d528  mov     eax, [rcx+2Ch]
0x18000d52b  test    al, 1
0x18000d52d  jz      short loc_18000D544
0x18000d52f  mov     edx, 12h
0x18000d534  mov     [rsp+88h+var_68], edi
0x18000d538  mov     r9, rbx
0x18000d53b  mov     rcx, [rcx+18h]
0x18000d53f  call    WPP_SF_qL
0x18000d544  lea     rcx, [rsp+88h+arg_0]; this
0x18000d54c  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d551  mov     eax, 0C000000Dh
0x18000d556  lea     r11, [rsp+88h+var_8]
0x18000d55e  mov     rbx, [r11+18h]
0x18000d562  mov     rsi, [r11+20h]
0x18000d566  mov     rsp, r11
0x18000d569  pop     rdi
0x18000d56a  retn
```
