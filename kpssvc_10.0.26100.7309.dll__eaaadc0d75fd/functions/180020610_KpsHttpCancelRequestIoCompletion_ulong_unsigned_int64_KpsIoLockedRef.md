# KpsHttpCancelRequestIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x180020610`
- end: `0x18002073e`
- name: `?KpsHttpCancelRequestIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
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
- `0x180020610`
- `0x180024be0`
- `0x180026a08`
- `0x180026de0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800206ee`
- `ntdll!RtlLeaveCriticalSection` at `0x1800206ee`

## string_xrefs

- `0x180020678`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsHttpCancelRequestIoCompletion(unsigned int a1, __int64 a2, struct KpsIoLockedRef *a3)
{
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // [rsp+28h] [rbp-10h]

  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, a3, *(_QWORD *)a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      LODWORD(v7) = 2129;
      WPP_SF_Dsd(
        v6[2],
        115,
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
    WPP_SF_(v6[2], 116, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
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
    WPP_SF_D(v6[2], 117, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v5);
}

```

## disassembly

```asm
0x180020610  mov     r11, rsp
0x180020613  mov     [r11+8], rbx
0x180020617  mov     [r11+10h], rbp
0x18002061b  mov     [r11+18h], rsi
0x18002061f  push    rdi
0x180020620  sub     rsp, 30h
0x180020624  mov     rbx, r8
0x180020627  mov     rax, rdx
0x18002062a  mov     edi, ecx
0x18002062c  xor     esi, esi
0x18002062e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020635  lea     rbp, WPP_GLOBAL_Control
0x18002063c  cmp     rcx, rbp
0x18002063f  jz      short loc_180020665
0x180020641  test    byte ptr [rcx+1Ch], 20h
0x180020645  jz      short loc_180020665
0x180020647  mov     r9, [r8]
0x18002064a  lea     edx, [rsi+72h]
0x18002064d  mov     rcx, [rcx+10h]
0x180020651  mov     [r11-10h], rax
0x180020655  mov     dword ptr [rsp+38h+var_18], edi
0x180020659  call    WPP_SF_qDI
0x18002065e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020665  test    edi, edi
0x180020667  jz      short loc_1800206AB
0x180020669  cmp     rcx, rbp
0x18002066c  jz      short loc_1800206A7
0x18002066e  test    byte ptr [rcx+1Ch], 1
0x180020672  jz      short loc_1800206A7
0x180020674  mov     rcx, [rcx+10h]
0x180020678  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18002067f  mov     edx, 73h ; 's'
0x180020684  mov     [rsp+38h+var_10], 851h
0x18002068c  mov     r9d, edi
0x18002068f  mov     [rsp+38h+var_18], rax
0x180020694  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002069b  call    WPP_SF_Dsd
0x1800206a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206a7  mov     esi, edi
0x1800206a9  jmp     short loc_1800206D2
0x1800206ab  cmp     rcx, rbp
0x1800206ae  jz      short loc_1800206D2
0x1800206b0  test    byte ptr [rcx+1Ch], 4
0x1800206b4  jz      short loc_1800206D2
0x1800206b6  mov     rcx, [rcx+10h]
0x1800206ba  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800206c1  mov     edx, 74h ; 't'
0x1800206c6  call    WPP_SF_
0x1800206cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206d2  cmp     qword ptr [rbx], 0
0x1800206d6  jz      short loc_180020705
0x1800206d8  mov     rcx, rbx; this
0x1800206db  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x1800206e0  test    al, al
0x1800206e2  jnz     short loc_1800206FA
0x1800206e4  mov     rcx, [rbx]
0x1800206e7  add     rcx, 120h; CriticalSection
0x1800206ee  call    cs:__imp_RtlLeaveCriticalSection
0x1800206f5  nop     dword ptr [rax+rax+00h]
0x1800206fa  and     qword ptr [rbx], 0
0x1800206fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180020705  cmp     rcx, rbp
0x180020708  jz      short loc_180020728
0x18002070a  test    byte ptr [rcx+1Ch], 20h
0x18002070e  jz      short loc_180020728
0x180020710  mov     rcx, [rcx+10h]
0x180020714  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002071b  mov     edx, 75h ; 'u'
0x180020720  mov     r9d, esi
0x180020723  call    WPP_SF_D
0x180020728  mov     rbx, [rsp+38h+arg_0]
0x18002072d  mov     rbp, [rsp+38h+arg_8]
0x180020732  mov     rsi, [rsp+38h+arg_10]
0x180020737  add     rsp, 30h
0x18002073b  pop     rdi
0x18002073c  retn
```
