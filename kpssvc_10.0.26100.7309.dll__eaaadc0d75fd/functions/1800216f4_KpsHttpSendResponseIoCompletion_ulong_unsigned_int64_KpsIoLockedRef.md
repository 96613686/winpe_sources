# KpsHttpSendResponseIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x1800216f4`
- end: `0x180021822`
- name: `?KpsHttpSendResponseIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
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
- `0x1800216f4`
- `0x180024be0`
- `0x180026a08`
- `0x180026de0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800217d2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800217d2`

## string_xrefs

- `0x18002175c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpSendResponseIoCompletion(unsigned int a1, __int64 a2, struct KpsIoLockedRef *a3)
{
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // [rsp+28h] [rbp-10h]

  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, a3, *(_QWORD *)a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      LODWORD(v7) = 1942;
      WPP_SF_Dsd(
        v6[2],
        98,
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
    WPP_SF_(v6[2], 99, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
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
    WPP_SF_D(v6[2], 100, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v5);
}

```

## disassembly

```asm
0x1800216f4  mov     r11, rsp
0x1800216f7  mov     [r11+8], rbx
0x1800216fb  mov     [r11+10h], rbp
0x1800216ff  mov     [r11+18h], rsi
0x180021703  push    rdi
0x180021704  sub     rsp, 30h
0x180021708  mov     rbx, r8
0x18002170b  mov     rax, rdx
0x18002170e  mov     edi, ecx
0x180021710  xor     esi, esi
0x180021712  mov     rcx, cs:WPP_GLOBAL_Control
0x180021719  lea     rbp, WPP_GLOBAL_Control
0x180021720  cmp     rcx, rbp
0x180021723  jz      short loc_180021749
0x180021725  test    byte ptr [rcx+1Ch], 20h
0x180021729  jz      short loc_180021749
0x18002172b  mov     r9, [r8]
0x18002172e  lea     edx, [rsi+61h]
0x180021731  mov     rcx, [rcx+10h]
0x180021735  mov     [r11-10h], rax
0x180021739  mov     dword ptr [rsp+38h+var_18], edi
0x18002173d  call    WPP_SF_qDI
0x180021742  mov     rcx, cs:WPP_GLOBAL_Control
0x180021749  test    edi, edi
0x18002174b  jz      short loc_18002178F
0x18002174d  cmp     rcx, rbp
0x180021750  jz      short loc_18002178B
0x180021752  test    byte ptr [rcx+1Ch], 1
0x180021756  jz      short loc_18002178B
0x180021758  mov     rcx, [rcx+10h]
0x18002175c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180021763  mov     edx, 62h ; 'b'
0x180021768  mov     [rsp+38h+var_10], 796h
0x180021770  mov     r9d, edi
0x180021773  mov     [rsp+38h+var_18], rax
0x180021778  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002177f  call    WPP_SF_Dsd
0x180021784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002178b  mov     esi, edi
0x18002178d  jmp     short loc_1800217B6
0x18002178f  cmp     rcx, rbp
0x180021792  jz      short loc_1800217B6
0x180021794  test    byte ptr [rcx+1Ch], 4
0x180021798  jz      short loc_1800217B6
0x18002179a  mov     rcx, [rcx+10h]
0x18002179e  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800217a5  mov     edx, 63h ; 'c'
0x1800217aa  call    WPP_SF_
0x1800217af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217b6  cmp     qword ptr [rbx], 0
0x1800217ba  jz      short loc_1800217E9
0x1800217bc  mov     rcx, rbx; this
0x1800217bf  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x1800217c4  test    al, al
0x1800217c6  jnz     short loc_1800217DE
0x1800217c8  mov     rcx, [rbx]
0x1800217cb  add     rcx, 120h; CriticalSection
0x1800217d2  call    cs:__imp_RtlLeaveCriticalSection
0x1800217d9  nop     dword ptr [rax+rax+00h]
0x1800217de  and     qword ptr [rbx], 0
0x1800217e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217e9  cmp     rcx, rbp
0x1800217ec  jz      short loc_18002180C
0x1800217ee  test    byte ptr [rcx+1Ch], 20h
0x1800217f2  jz      short loc_18002180C
0x1800217f4  mov     rcx, [rcx+10h]
0x1800217f8  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800217ff  mov     edx, 64h ; 'd'
0x180021804  mov     r9d, esi
0x180021807  call    WPP_SF_D
0x18002180c  mov     rbx, [rsp+38h+arg_0]
0x180021811  mov     rbp, [rsp+38h+arg_8]
0x180021816  mov     rsi, [rsp+38h+arg_10]
0x18002181b  add     rsp, 30h
0x18002181f  pop     rdi
0x180021820  retn
```
