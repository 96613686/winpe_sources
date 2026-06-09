# KpsHttpSendPostResponseIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x1800215c0`
- end: `0x1800216ee`
- name: `?KpsHttpSendPostResponseIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `302`
- prototype: `void __fastcall(unsigned int, __int64, struct KpsIoLockedRef *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x1800215c0`
- `0x180024be0`
- `0x180026a08`
- `0x180026de0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002169e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002169e`

## string_xrefs

- `0x180021628`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpSendPostResponseIoCompletion(unsigned int a1, __int64 a2, struct KpsIoLockedRef *a3)
{
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // [rsp+28h] [rbp-10h]

  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, a3, *(_QWORD *)a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      LODWORD(v7) = 1972;
      WPP_SF_Dsd(
        v6[2],
        102,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        a1,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        v7);
      v6 = WPP_GLOBAL_Control;
    }
    v5 = a1;
  }
  else if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
  {
    WPP_SF_(v6[2], 103, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)a3 )
  {
    if ( !KpsIoLockedRef::RemoveRef(a3) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)a3 + 288LL));
    *(_QWORD *)a3 = 0;
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_D(v6[2], 104, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v5);
}

```

## disassembly

```asm
0x1800215c0  mov     r11, rsp
0x1800215c3  mov     [r11+8], rbx
0x1800215c7  mov     [r11+10h], rbp
0x1800215cb  mov     [r11+18h], rsi
0x1800215cf  push    rdi
0x1800215d0  sub     rsp, 30h
0x1800215d4  mov     rbx, r8
0x1800215d7  mov     rax, rdx
0x1800215da  mov     edi, ecx
0x1800215dc  xor     esi, esi
0x1800215de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215e5  lea     rbp, WPP_GLOBAL_Control
0x1800215ec  cmp     rcx, rbp
0x1800215ef  jz      short loc_180021615
0x1800215f1  test    byte ptr [rcx+1Ch], 20h
0x1800215f5  jz      short loc_180021615
0x1800215f7  mov     r9, [r8]
0x1800215fa  lea     edx, [rsi+65h]
0x1800215fd  mov     rcx, [rcx+10h]
0x180021601  mov     [r11-10h], rax
0x180021605  mov     dword ptr [rsp+38h+var_18], edi
0x180021609  call    WPP_SF_qDI
0x18002160e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021615  test    edi, edi
0x180021617  jz      short loc_18002165B
0x180021619  cmp     rcx, rbp
0x18002161c  jz      short loc_180021657
0x18002161e  test    byte ptr [rcx+1Ch], 1
0x180021622  jz      short loc_180021657
0x180021624  mov     rcx, [rcx+10h]
0x180021628  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18002162f  mov     edx, 66h ; 'f'
0x180021634  mov     [rsp+38h+var_10], 7B4h
0x18002163c  mov     r9d, edi
0x18002163f  mov     [rsp+38h+var_18], rax
0x180021644  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002164b  call    WPP_SF_Dsd
0x180021650  mov     rcx, cs:WPP_GLOBAL_Control
0x180021657  mov     esi, edi
0x180021659  jmp     short loc_180021682
0x18002165b  cmp     rcx, rbp
0x18002165e  jz      short loc_180021682
0x180021660  test    byte ptr [rcx+1Ch], 4
0x180021664  jz      short loc_180021682
0x180021666  mov     rcx, [rcx+10h]
0x18002166a  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021671  mov     edx, 67h ; 'g'
0x180021676  call    WPP_SF_
0x18002167b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021682  cmp     qword ptr [rbx], 0
0x180021686  jz      short loc_1800216B5
0x180021688  mov     rcx, rbx; this
0x18002168b  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180021690  test    al, al
0x180021692  jnz     short loc_1800216AA
0x180021694  mov     rcx, [rbx]
0x180021697  add     rcx, 120h; CriticalSection
0x18002169e  call    cs:__imp_RtlLeaveCriticalSection
0x1800216a5  nop     dword ptr [rax+rax+00h]
0x1800216aa  and     qword ptr [rbx], 0
0x1800216ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216b5  cmp     rcx, rbp
0x1800216b8  jz      short loc_1800216D8
0x1800216ba  test    byte ptr [rcx+1Ch], 20h
0x1800216be  jz      short loc_1800216D8
0x1800216c0  mov     rcx, [rcx+10h]
0x1800216c4  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800216cb  mov     edx, 68h ; 'h'
0x1800216d0  mov     r9d, esi
0x1800216d3  call    WPP_SF_D
0x1800216d8  mov     rbx, [rsp+38h+arg_0]
0x1800216dd  mov     rbp, [rsp+38h+arg_8]
0x1800216e2  mov     rsi, [rsp+38h+arg_10]
0x1800216e7  add     rsp, 30h
0x1800216eb  pop     rdi
0x1800216ec  retn
```
