# ReadCeremonyDataWork::WorkCallback(void)

- ea: `0x18000bee0`
- end: `0x18000c00e`
- name: `?WorkCallback@ReadCeremonyDataWork@@UEAAXXZ`
- size: `302`
- prototype: `void __fastcall(CWiGigDAFProviderAssociation **this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800014d0`
- `0x180001ef4`
- `0x18000a428`
- `0x18000bee0`
- `0x18000c308`
- `0x18000c348`
- `0x18001f010`

## pseudocode

```c
void __fastcall ReadCeremonyDataWork::WorkCallback(CWiGigDAFProviderAssociation **this)
{
  struct DAF_CEREMONY_DATA_PIN *v2; // rax
  struct DAF_CEREMONY_DATA_PIN *v3; // rbx
  int CeremonyData; // eax
  unsigned int v5; // esi
  __int64 v6; // r9
  struct DAF_CEREMONY_DATA_PIN *v7; // r8
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  v2 = (struct DAF_CEREMONY_DATA_PIN *)operator new(0x218u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    CeremonyData = CWiGigDAFProviderAssociation::ReadCeremonyData(this[2], v2);
    v5 = CeremonyData;
    if ( CeremonyData >= 0 )
    {
      v6 = 0;
      v7 = v3;
      v8 = 536;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_c2da2149000737c368804296c411cd66_Traceguids,
          this[2],
          CeremonyData);
      }
      v6 = v5;
      v7 = 0;
      v8 = 0;
    }
    (*(void (__fastcall **)(CWiGigDAFProviderAssociation *, __int64, struct DAF_CEREMONY_DATA_PIN *, __int64))(*(_QWORD *)this[1] + 24LL))(
      this[1],
      v8,
      v7,
      v6);
  }
  else
  {
    (*(void (__fastcall **)(CWiGigDAFProviderAssociation *, _QWORD, _QWORD, __int64))(*(_QWORD *)this[1] + 24LL))(
      this[1],
      0,
      0,
      2147942414LL);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  if ( v3 )
    operator delete(v3);
}

```

## disassembly

```asm
0x18000bee0  push    rbx
0x18000bee2  push    rsi
0x18000bee3  push    rdi
0x18000bee4  push    r14
0x18000bee6  sub     rsp, 38h
0x18000beea  mov     rdi, rcx
0x18000beed  lea     r14, WPP_GLOBAL_Control
0x18000bef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000befb  cmp     rcx, r14
0x18000befe  jz      short loc_18000BF24
0x18000bf00  cmp     byte ptr [rcx+19h], 4
0x18000bf04  jb      short loc_18000BF24
0x18000bf06  test    byte ptr [rcx+1Ch], 1
0x18000bf0a  jz      short loc_18000BF24
0x18000bf0c  mov     edx, 18h
0x18000bf11  mov     r9, rdi
0x18000bf14  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000bf1b  mov     rcx, [rcx+10h]
0x18000bf1f  call    WPP_SF_q
0x18000bf24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf2b  mov     ecx, 218h; unsigned __int64
0x18000bf30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bf35  mov     rbx, rax
0x18000bf38  mov     [rsp+58h+arg_8], rax
0x18000bf3d  test    rax, rax
0x18000bf40  jnz     short loc_18000BF5A
0x18000bf42  mov     rcx, [rdi+8]
0x18000bf46  mov     rdx, [rcx]
0x18000bf49  mov     rax, [rdx+18h]
0x18000bf4d  mov     r9d, 8007000Eh
0x18000bf53  xor     r8d, r8d
0x18000bf56  xor     edx, edx
0x18000bf58  jmp     short loc_18000BFC1
0x18000bf5a  mov     rdx, rbx; struct DAF_CEREMONY_DATA_PIN *
0x18000bf5d  mov     rcx, [rdi+10h]; this
0x18000bf61  call    ?ReadCeremonyData@CWiGigDAFProviderAssociation@@QEAAJPEAUDAF_CEREMONY_DATA_PIN@@@Z; CWiGigDAFProviderAssociation::ReadCeremonyData(DAF_CEREMONY_DATA_PIN *)
0x18000bf66  mov     esi, eax
0x18000bf68  test    eax, eax
0x18000bf6a  jns     short loc_18000BFAB
0x18000bf6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf73  cmp     rcx, r14
0x18000bf76  jz      short loc_18000BFA1
0x18000bf78  cmp     byte ptr [rcx+19h], 1
0x18000bf7c  jb      short loc_18000BFA1
0x18000bf7e  test    byte ptr [rcx+1Ch], 1
0x18000bf82  jz      short loc_18000BFA1
0x18000bf84  mov     edx, 19h
0x18000bf89  mov     [rsp+58h+var_38], eax
0x18000bf8d  mov     r9, [rdi+10h]
0x18000bf91  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000bf98  mov     rcx, [rcx+10h]
0x18000bf9c  call    WPP_SF_qD
0x18000bfa1  mov     r9d, esi
0x18000bfa4  xor     r8d, r8d
0x18000bfa7  xor     edx, edx
0x18000bfa9  jmp     short loc_18000BFB6
0x18000bfab  xor     r9d, r9d
0x18000bfae  mov     r8, rbx
0x18000bfb1  mov     edx, 218h
0x18000bfb6  mov     rcx, [rdi+8]
0x18000bfba  mov     rax, [rcx]
0x18000bfbd  mov     rax, [rax+18h]
0x18000bfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfcd  cmp     rcx, r14
0x18000bfd0  jz      short loc_18000BFF7
0x18000bfd2  cmp     byte ptr [rcx+19h], 4
0x18000bfd6  jb      short loc_18000BFF7
0x18000bfd8  test    byte ptr [rcx+1Ch], 1
0x18000bfdc  jz      short loc_18000BFF7
0x18000bfde  mov     edx, 1Ah
0x18000bfe3  mov     r9, rdi
0x18000bfe6  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000bfed  mov     rcx, [rcx+10h]
0x18000bff1  call    WPP_SF_q
0x18000bff6  nop
0x18000bff7  test    rbx, rbx
0x18000bffa  jz      short loc_18000C004
0x18000bffc  mov     rcx, rbx; Block
0x18000bfff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c004  add     rsp, 38h
0x18000c008  pop     r14
0x18000c00a  pop     rdi
0x18000c00b  pop     rsi
0x18000c00c  pop     rbx
0x18000c00d  retn
```
