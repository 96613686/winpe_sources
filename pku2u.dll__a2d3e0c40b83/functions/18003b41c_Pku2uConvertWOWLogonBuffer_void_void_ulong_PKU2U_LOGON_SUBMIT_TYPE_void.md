# Pku2uConvertWOWLogonBuffer(void *,void *,ulong *,_PKU2U_LOGON_SUBMIT_TYPE,void * *)

- ea: `0x18003b41c`
- end: `0x18003b58b`
- name: `?Pku2uConvertWOWLogonBuffer@@YAJPEAX0PEAKW4_PKU2U_LOGON_SUBMIT_TYPE@@PEAPEAX@Z`
- size: `367`
- prototype: `__int64 __fastcall(void *, void *, unsigned int *, enum _PKU2U_LOGON_SUBMIT_TYPE, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002cf50`

## callees

- `0x180018870`
- `0x180023d9c`
- `0x18003b41c`
- `0x180044f8c`

## string_xrefs

- `0x18003b44f`: `onecore\ds\security\protocols\pku2u\wow.cxx`
- `0x18003b4a6`: `onecore\ds\security\protocols\pku2u\wow.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uConvertWOWLogonBuffer(
        _DWORD *a1,
        void *a2,
        unsigned int *a3,
        enum _PKU2U_LOGON_SUBMIT_TYPE a4,
        void **a5)
{
  unsigned int v8; // esi
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax

  if ( a4 == Pku2uCertificateS4ULogon )
  {
    v8 = *a3 + 24;
    if ( v8 >= 0x38 )
    {
      v9 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v8);
      v10 = v9;
      if ( v9 )
      {
        *v9 = *a1;
        v9[1] = a1[1];
        memcpy_0(v9 + 14, a1 + 8, *a3 - 32);
        *((_WORD *)v10 + 4) = *((_WORD *)a1 + 4);
        *((_WORD *)v10 + 5) = *((_WORD *)a1 + 5);
        if ( a1[3] )
          v11 = (unsigned int)a1[3] + 24LL;
        else
          v11 = 0;
        *((_QWORD *)v10 + 2) = v11;
        *((_WORD *)v10 + 12) = *((_WORD *)a1 + 8);
        *((_WORD *)v10 + 13) = *((_WORD *)a1 + 9);
        if ( a1[5] )
          v12 = (unsigned int)a1[5] + 24LL;
        else
          v12 = 0;
        *((_QWORD *)v10 + 4) = v12;
        v10[10] = a1[6];
        *((_QWORD *)v10 + 6) = (unsigned int)a1[7] + 24LL;
        *a3 = v8;
        *a5 = v10;
        return 0;
      }
      else
      {
        return 3221225495LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_f44eef53fbbe3417db0d33b0825189c4_Traceguids,
          v8,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\wow.cxx",
          90);
      return 3221225485LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_f44eef53fbbe3417db0d33b0825189c4_Traceguids,
        a4,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\wow.cxx",
        145);
    return 3221225475LL;
  }
}

```

## disassembly

```asm
0x18003b41c  push    rbx
0x18003b41e  push    rsi
0x18003b41f  push    rdi
0x18003b420  push    r14
0x18003b422  sub     rsp, 38h
0x18003b426  mov     r14, r8
0x18003b429  mov     rdi, rcx
0x18003b42c  cmp     r9d, 0Eh
0x18003b430  jz      short loc_18003B47E
0x18003b432  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b439  lea     rax, WPP_GLOBAL_Control
0x18003b440  cmp     rcx, rax
0x18003b443  jz      short loc_18003B474
0x18003b445  test    byte ptr [rcx+1Ch], 1
0x18003b449  jz      short loc_18003B474
0x18003b44b  mov     rcx, [rcx+10h]
0x18003b44f  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\protocols\\pku2u"...
0x18003b456  mov     edx, 0Bh
0x18003b45b  mov     [rsp+58h+var_30], 91h
0x18003b463  lea     r8, WPP_f44eef53fbbe3417db0d33b0825189c4_Traceguids
0x18003b46a  mov     [rsp+58h+var_38], rax
0x18003b46f  call    WPP_SF_dsd
0x18003b474  mov     eax, 0C0000003h
0x18003b479  jmp     loc_18003B581
0x18003b47e  mov     esi, [r8]
0x18003b481  add     esi, 18h
0x18003b484  cmp     esi, 38h ; '8'
0x18003b487  jnb     short loc_18003B4D8
0x18003b489  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b490  lea     rax, WPP_GLOBAL_Control
0x18003b497  cmp     rcx, rax
0x18003b49a  jz      short loc_18003B4CE
0x18003b49c  test    byte ptr [rcx+1Ch], 1
0x18003b4a0  jz      short loc_18003B4CE
0x18003b4a2  mov     rcx, [rcx+10h]
0x18003b4a6  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\protocols\\pku2u"...
0x18003b4ad  mov     edx, 0Ah
0x18003b4b2  mov     [rsp+58h+var_30], 5Ah ; 'Z'
0x18003b4ba  mov     r9d, esi
0x18003b4bd  mov     [rsp+58h+var_38], rax
0x18003b4c2  lea     r8, WPP_f44eef53fbbe3417db0d33b0825189c4_Traceguids
0x18003b4c9  call    WPP_SF_dsd
0x18003b4ce  mov     eax, 0C000000Dh
0x18003b4d3  jmp     loc_18003B581
0x18003b4d8  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003b4df  mov     edx, esi; unsigned __int64
0x18003b4e1  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18003b4e6  mov     rbx, rax
0x18003b4e9  test    rax, rax
0x18003b4ec  jnz     short loc_18003B4F8
0x18003b4ee  mov     eax, 0C0000017h
0x18003b4f3  jmp     loc_18003B581
0x18003b4f8  mov     eax, [rdi]
0x18003b4fa  lea     rdx, [rdi+20h]; Src
0x18003b4fe  mov     [rbx], eax
0x18003b500  lea     rcx, [rbx+38h]; void *
0x18003b504  mov     eax, [rdi+4]
0x18003b507  mov     [rbx+4], eax
0x18003b50a  mov     r8d, [r14]
0x18003b50d  sub     r8d, 20h ; ' '; Size
0x18003b511  call    memcpy_0
0x18003b516  movzx   eax, word ptr [rdi+8]
0x18003b51a  mov     [rbx+8], ax
0x18003b51e  movzx   eax, word ptr [rdi+0Ah]
0x18003b522  mov     [rbx+0Ah], ax
0x18003b526  cmp     dword ptr [rdi+0Ch], 0
0x18003b52a  jnz     short loc_18003B530
0x18003b52c  xor     eax, eax
0x18003b52e  jmp     short loc_18003B537
0x18003b530  mov     eax, [rdi+0Ch]
0x18003b533  add     rax, 18h
0x18003b537  mov     [rbx+10h], rax
0x18003b53b  movzx   eax, word ptr [rdi+10h]
0x18003b53f  mov     [rbx+18h], ax
0x18003b543  movzx   eax, word ptr [rdi+12h]
0x18003b547  mov     [rbx+1Ah], ax
0x18003b54b  cmp     dword ptr [rdi+14h], 0
0x18003b54f  jnz     short loc_18003B555
0x18003b551  xor     eax, eax
0x18003b553  jmp     short loc_18003B55C
0x18003b555  mov     eax, [rdi+14h]
0x18003b558  add     rax, 18h
0x18003b55c  mov     [rbx+20h], rax
0x18003b560  mov     eax, [rdi+18h]
0x18003b563  mov     [rbx+28h], eax
0x18003b566  mov     eax, [rdi+1Ch]
0x18003b569  add     rax, 18h
0x18003b56d  mov     [rbx+30h], rax
0x18003b571  mov     rax, [rsp+58h+arg_20]
0x18003b579  mov     [r14], esi
0x18003b57c  mov     [rax], rbx
0x18003b57f  xor     eax, eax
0x18003b581  add     rsp, 38h
0x18003b585  pop     r14
0x18003b587  pop     rdi
0x18003b588  pop     rsi
0x18003b589  pop     rbx
0x18003b58a  retn
```
