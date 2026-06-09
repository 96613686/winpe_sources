# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002300`
- end: `0x1800023ac`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023c0`

## callees

- `0x180002300`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 504504970 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data2
        || a2[2] != *(_DWORD *)GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data4
        || a2[3] != *(_DWORD *)&GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
    }
    else
    {
      if ( *a2 != 1302534674
        || a2[1] != *(_DWORD *)&GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data2
        || a2[2] != *(_DWORD *)GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4
        || a2[3] != *(_DWORD *)&GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
      a1 += 8;
    }
    *a3 = a1;
    goto LABEL_6;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    return (unsigned int)-2147467262;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180002300  push    rbx
0x180002302  sub     rsp, 20h
0x180002306  xor     ebx, ebx
0x180002308  mov     [r8], rbx
0x18000230b  cmp     [rdx], ebx
0x18000230d  jnz     short loc_180002341
0x18000230f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180002315  cmp     [rdx+4], eax
0x180002318  jnz     short loc_18000236A
0x18000231a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180002320  cmp     [rdx+8], eax
0x180002323  jnz     short loc_18000236A
0x180002325  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000232b  cmp     [rdx+0Ch], eax
0x18000232e  jnz     short loc_18000236A
0x180002330  mov     [r8], rcx
0x180002333  mov     rax, [rcx]
0x180002336  mov     rax, [rax+8]
0x18000233a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233f  jmp     short loc_18000236F
0x180002341  cmp     dword ptr [rdx], 1E12228Ah
0x180002347  jnz     short loc_180002377
0x180002349  mov     eax, dword ptr cs:_GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data2
0x18000234f  cmp     [rdx+4], eax
0x180002352  jnz     short loc_18000236A
0x180002354  mov     eax, dword ptr cs:_GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data4
0x18000235a  cmp     [rdx+8], eax
0x18000235d  jnz     short loc_18000236A
0x18000235f  mov     eax, dword ptr cs:_GUID_1e12228a_aef9_4e6d_8c33_a192dbf0e25f.Data4+4
0x180002365  cmp     [rdx+0Ch], eax
0x180002368  jz      short loc_1800023A4
0x18000236a  mov     ebx, 80004002h
0x18000236f  mov     eax, ebx
0x180002371  add     rsp, 20h
0x180002375  pop     rbx
0x180002376  retn
0x180002377  cmp     dword ptr [rdx], 4DA31A12h
0x18000237d  jnz     short loc_18000236A
0x18000237f  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data2
0x180002385  cmp     [rdx+4], eax
0x180002388  jnz     short loc_18000236A
0x18000238a  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4
0x180002390  cmp     [rdx+8], eax
0x180002393  jnz     short loc_18000236A
0x180002395  mov     eax, dword ptr cs:_GUID_4da31a12_cc32_49bc_b2cc_060dbcf2bafc.Data4+4
0x18000239b  cmp     [rdx+0Ch], eax
0x18000239e  jnz     short loc_18000236A
0x1800023a0  add     rcx, 8
0x1800023a4  mov     rax, rcx
0x1800023a7  mov     [r8], rcx
0x1800023aa  jmp     short loc_180002333
```
