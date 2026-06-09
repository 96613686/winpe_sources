# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)

- ea: `0x140002330`
- end: `0x140002479`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByVal@$00@@U1@U_tlgWrapperPtrSize@@U6@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByVal@$00@@3AEBU_tlgWrapperPtrSize@@8@Z`
- size: `329`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fd68`
- `0x14000fe8c`

## callees

- `0x1400019e8`
- `0x140002330`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 *a14,
        __int64 *a15)
{
  int v17; // edx
  const WCHAR *v18; // rcx
  __int64 v19; // rax
  _BYTE v21[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  const WCHAR *v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  int v45; // [rsp+F8h] [rbp-8h]
  int v46; // [rsp+FCh] [rbp-4h]

  v40 = 8;
  v46 = 0;
  v43 = 0;
  v38 = 1;
  v17 = 2;
  v44 = *a15;
  v45 = *((_DWORD *)a15 + 2);
  v36 = 4;
  v34 = 4;
  v41 = *a14;
  v42 = *((_DWORD *)a14 + 2);
  v39 = a13;
  v37 = a12;
  v35 = a11;
  v33 = a10;
  v31 = a9;
  v29 = a8;
  v32 = 2;
  v30 = 4;
  v18 = *a7;
  if ( *a7 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v17 = 2 * v19 + 2;
  }
  else
  {
    v18 = &String;
  }
  v24 = a6;
  v22 = a5;
  v26 = v18;
  v27 = v17;
  v28 = 0;
  v25 = 4;
  v23 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 13, v21);
}

```

## disassembly

```asm
0x140002330  push    rbp
0x140002332  lea     rbp, [rsp-10h]
0x140002337  sub     rsp, 110h
0x14000233e  mov     rax, cs:__security_cookie
0x140002345  xor     rax, rsp
0x140002348  mov     [rbp+10h+var_10], rax
0x14000234c  mov     r10, rcx
0x14000234f  mov     [rbp+10h+var_38], 8
0x140002357  mov     rcx, [rbp+10h+arg_70]
0x14000235e  xor     r8d, r8d
0x140002361  mov     r11, rdx
0x140002364  mov     [rbp+10h+var_14], r8d
0x140002368  mov     [rbp+10h+var_24], r8d
0x14000236c  mov     [rbp+10h+var_48], 1
0x140002374  mov     rax, [rcx]
0x140002377  lea     edx, [r8+2]
0x14000237b  mov     [rbp+10h+var_20], rax
0x14000237f  mov     eax, [rcx+8]
0x140002382  mov     rcx, [rbp+10h+arg_68]
0x140002389  mov     [rbp+10h+var_18], eax
0x14000238c  mov     [rbp+10h+var_58], 4
0x140002394  mov     [rbp+10h+var_68], 4
0x14000239c  mov     rax, [rcx]
0x14000239f  mov     [rbp+10h+var_30], rax
0x1400023a3  mov     eax, [rcx+8]
0x1400023a6  mov     [rbp+10h+var_28], eax
0x1400023a9  mov     rax, [rbp+10h+arg_60]
0x1400023b0  mov     [rbp+10h+var_40], rax
0x1400023b4  mov     rax, [rbp+10h+arg_58]
0x1400023b8  mov     [rbp+10h+var_50], rax
0x1400023bc  mov     rax, [rbp+10h+arg_50]
0x1400023c0  mov     [rbp+10h+var_60], rax
0x1400023c4  mov     rax, [rbp+10h+arg_48]
0x1400023c8  mov     [rbp+10h+var_70], rax
0x1400023cc  mov     rax, [rbp+10h+arg_40]
0x1400023d0  mov     [rbp+10h+var_80], rax
0x1400023d4  mov     rax, [rbp+10h+arg_38]
0x1400023d8  mov     [rbp+10h+var_90], rax
0x1400023dc  mov     rax, [rbp+10h+arg_30]
0x1400023e0  mov     [rbp+10h+var_78], rdx
0x1400023e4  mov     [rbp+10h+var_88], 4
0x1400023ec  mov     rcx, [rax]
0x1400023ef  test    rcx, rcx
0x1400023f2  jz      short loc_14000240B
0x1400023f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400023f8  inc     rax
0x1400023fb  cmp     [rcx+rax*2], r8w
0x140002400  jnz     short loc_1400023F8
0x140002402  lea     edx, ds:2[rax*2]
0x140002409  jmp     short loc_140002412
0x14000240b  lea     rcx, String
0x140002412  mov     rax, [rbp+10h+arg_28]
0x140002416  xor     r9d, r9d
0x140002419  mov     [rsp+110h+var_B0], rax
0x14000241e  mov     rax, [rbp+10h+arg_20]
0x140002422  mov     [rsp+110h+var_C0], rax
0x140002427  lea     rax, [rsp+110h+var_E0]
0x14000242c  mov     [rsp+110h+var_A0], rcx
0x140002431  mov     rcx, r10
0x140002434  mov     [rsp+110h+var_98], edx
0x140002438  mov     rdx, r11
0x14000243b  mov     [rsp+110h+var_E8], rax
0x140002440  mov     [rsp+110h+var_F0], 0Dh
0x140002448  mov     [rsp+110h+var_94], r8d
0x14000244d  mov     [rsp+110h+var_A8], 4
0x140002456  mov     [rsp+110h+var_B8], 8
0x14000245f  call    _tlgWriteTransfer_EventWriteTransfer
0x140002464  mov     rcx, [rbp+10h+var_10]
0x140002468  xor     rcx, rsp; StackCookie
0x14000246b  call    __security_check_cookie
0x140002470  add     rsp, 110h
0x140002477  pop     rbp
0x140002478  retn
```
