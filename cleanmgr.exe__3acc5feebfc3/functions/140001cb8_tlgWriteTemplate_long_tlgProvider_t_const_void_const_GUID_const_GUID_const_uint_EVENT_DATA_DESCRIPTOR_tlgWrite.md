# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<8> const &,_tlgWrapperArray<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)

- ea: `0x140001cb8`
- end: `0x140001fad`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U1@U1@U1@U1@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U1@U1@U?$_tlgWrapperArray@$07@@U4@U_tlgWrapperPtrSize@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5553333555555555533AEBU?$_tlgWrapperArray@$07@@6AEBU_tlgWrapperPtrSize@@7@Z`
- size: `757`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014fe0`

## callees

- `0x1400019e8`
- `0x140001cb8`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const WCHAR **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 *a27,
        __int64 *a28,
        __int64 *a29,
        __int64 *a30)
{
  int v32; // edx
  const WCHAR *v33; // rcx
  __int64 v34; // rax
  _BYTE v36[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  const WCHAR *v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+6Ch] [rbp-94h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  __int64 v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h]
  __int64 v54; // [rsp+D0h] [rbp-30h]
  __int64 v55; // [rsp+D8h] [rbp-28h]
  __int64 v56; // [rsp+E0h] [rbp-20h]
  __int64 v57; // [rsp+E8h] [rbp-18h]
  __int64 v58; // [rsp+F0h] [rbp-10h]
  __int64 v59; // [rsp+F8h] [rbp-8h]
  __int64 v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  __int64 v64; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  __int64 v67; // [rsp+138h] [rbp+38h]
  __int64 v68; // [rsp+140h] [rbp+40h]
  __int64 v69; // [rsp+148h] [rbp+48h]
  __int64 v70; // [rsp+150h] [rbp+50h]
  __int64 v71; // [rsp+158h] [rbp+58h]
  __int64 v72; // [rsp+160h] [rbp+60h]
  __int64 v73; // [rsp+168h] [rbp+68h]
  __int64 v74; // [rsp+170h] [rbp+70h]
  __int64 v75; // [rsp+178h] [rbp+78h]
  __int64 v76; // [rsp+180h] [rbp+80h]
  __int64 v77; // [rsp+188h] [rbp+88h]
  __int64 v78; // [rsp+190h] [rbp+90h]
  __int64 v79; // [rsp+198h] [rbp+98h]
  __int64 v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1A8h] [rbp+A8h]
  __int64 *v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]
  __int64 v84; // [rsp+1C0h] [rbp+C0h]
  int v85; // [rsp+1C8h] [rbp+C8h]
  int v86; // [rsp+1CCh] [rbp+CCh]
  __int64 *v87; // [rsp+1D0h] [rbp+D0h]
  __int64 v88; // [rsp+1D8h] [rbp+D8h]
  __int64 v89; // [rsp+1E0h] [rbp+E0h]
  int v90; // [rsp+1E8h] [rbp+E8h]
  int v91; // [rsp+1ECh] [rbp+ECh]
  __int64 v92; // [rsp+1F0h] [rbp+F0h]
  int v93; // [rsp+1F8h] [rbp+F8h]
  int v94; // [rsp+1FCh] [rbp+FCh]
  __int64 v95; // [rsp+200h] [rbp+100h]
  int v96; // [rsp+208h] [rbp+108h]
  int v97; // [rsp+20Ch] [rbp+10Ch]

  v81 = 8;
  v97 = 0;
  v94 = 0;
  v32 = 2;
  v91 = 0;
  v88 = 2;
  v95 = *a30;
  v96 = *((_DWORD *)a30 + 2);
  v83 = 2;
  v86 = 0;
  v92 = *a29;
  v93 = *((_DWORD *)a29 + 2);
  v79 = 8;
  v77 = 4;
  v75 = 4;
  v73 = 4;
  v89 = *a28;
  v90 = 8 * *((unsigned __int16 *)a28 + 4);
  v87 = a28 + 1;
  v71 = 4;
  v69 = 4;
  v67 = 4;
  v84 = *a27;
  v85 = 8 * *((unsigned __int16 *)a27 + 4);
  v80 = a26;
  v78 = a25;
  v76 = a24;
  v74 = a23;
  v72 = a22;
  v70 = a21;
  v68 = a20;
  v66 = a19;
  v64 = a18;
  v62 = a17;
  v60 = a16;
  v58 = a15;
  v56 = a14;
  v54 = a13;
  v52 = a12;
  v82 = a27 + 1;
  v65 = 4;
  v63 = 4;
  v61 = 4;
  v59 = 4;
  v57 = 8;
  v55 = 8;
  v53 = 8;
  v50 = a11;
  v48 = a10;
  v46 = a9;
  v44 = a8;
  v42 = a7;
  v51 = 8;
  v49 = 4;
  v47 = 4;
  v33 = *a6;
  v45 = 4;
  v43 = 4;
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v32 = 2 * v34 + 2;
  }
  else
  {
    v33 = &String;
  }
  v37 = a5;
  v39 = v33;
  v40 = v32;
  v41 = 0;
  v38 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 30, v36);
}

```

## disassembly

```asm
0x140001cb8  push    rbp
0x140001cba  lea     rbp, [rsp-120h]
0x140001cc2  sub     rsp, 220h
0x140001cc9  mov     rax, cs:__security_cookie
0x140001cd0  xor     rax, rsp
0x140001cd3  mov     [rbp+120h+var_10], rax
0x140001cda  xor     r8d, r8d
0x140001cdd  mov     [rbp+120h+var_78], 8
0x140001ce8  mov     r10, rcx
0x140001ceb  mov     [rbp+120h+var_14], r8d
0x140001cf2  mov     rcx, [rbp+120h+arg_E8]
0x140001cf9  mov     r11, rdx
0x140001cfc  mov     [rbp+120h+var_24], r8d
0x140001d03  lea     edx, [r8+2]
0x140001d07  mov     [rbp+120h+var_34], r8d
0x140001d0e  mov     [rbp+120h+var_48], rdx
0x140001d15  mov     rax, [rcx]
0x140001d18  mov     [rbp+120h+var_20], rax
0x140001d1f  mov     eax, [rcx+8]
0x140001d22  mov     rcx, [rbp+120h+arg_E0]
0x140001d29  mov     [rbp+120h+var_18], eax
0x140001d2f  mov     [rbp+120h+var_68], rdx
0x140001d36  mov     [rbp+120h+var_54], r8d
0x140001d3d  mov     rax, [rcx]
0x140001d40  mov     [rbp+120h+var_30], rax
0x140001d47  mov     eax, [rcx+8]
0x140001d4a  mov     [rbp+120h+var_28], eax
0x140001d50  mov     rax, [rbp+120h+arg_D8]
0x140001d57  mov     [rbp+120h+var_88], 8
0x140001d62  mov     [rbp+120h+var_98], 4
0x140001d6d  mov     [rbp+120h+var_A8], 4
0x140001d75  lea     rcx, [rax+8]
0x140001d79  mov     [rbp+120h+var_B8], 4
0x140001d81  mov     rax, [rax]
0x140001d84  mov     [rbp+120h+var_40], rax
0x140001d8b  movzx   eax, word ptr [rcx]
0x140001d8e  shl     eax, 3
0x140001d91  mov     [rbp+120h+var_38], eax
0x140001d97  mov     rax, [rbp+120h+arg_D0]
0x140001d9e  mov     [rbp+120h+var_50], rcx
0x140001da5  mov     [rbp+120h+var_C8], 4
0x140001dad  mov     [rbp+120h+var_D8], 4
0x140001db5  lea     rcx, [rax+8]
0x140001db9  mov     [rbp+120h+var_E8], 4
0x140001dc1  mov     rax, [rax]
0x140001dc4  mov     [rbp+120h+var_60], rax
0x140001dcb  movzx   eax, word ptr [rcx]
0x140001dce  shl     eax, 3
0x140001dd1  mov     [rbp+120h+var_58], eax
0x140001dd7  mov     rax, [rbp+120h+arg_C8]
0x140001dde  mov     [rbp+120h+var_80], rax
0x140001de5  mov     rax, [rbp+120h+arg_C0]
0x140001dec  mov     [rbp+120h+var_90], rax
0x140001df3  mov     rax, [rbp+120h+arg_B8]
0x140001dfa  mov     [rbp+120h+var_A0], rax
0x140001e01  mov     rax, [rbp+120h+arg_B0]
0x140001e08  mov     [rbp+120h+var_B0], rax
0x140001e0c  mov     rax, [rbp+120h+arg_A8]
0x140001e13  mov     [rbp+120h+var_C0], rax
0x140001e17  mov     rax, [rbp+120h+arg_A0]
0x140001e1e  mov     [rbp+120h+var_D0], rax
0x140001e22  mov     rax, [rbp+120h+arg_98]
0x140001e29  mov     [rbp+120h+var_E0], rax
0x140001e2d  mov     rax, [rbp+120h+arg_90]
0x140001e34  mov     [rbp+120h+var_F0], rax
0x140001e38  mov     rax, [rbp+120h+arg_88]
0x140001e3f  mov     [rbp+120h+var_100], rax
0x140001e43  mov     rax, [rbp+120h+arg_80]
0x140001e4a  mov     [rbp+120h+var_110], rax
0x140001e4e  mov     rax, [rbp+120h+arg_78]
0x140001e55  mov     [rbp+120h+var_120], rax
0x140001e59  mov     rax, [rbp+120h+arg_70]
0x140001e60  mov     [rbp+120h+var_130], rax
0x140001e64  mov     rax, [rbp+120h+arg_68]
0x140001e6b  mov     [rbp+120h+var_140], rax
0x140001e6f  mov     rax, [rbp+120h+arg_60]
0x140001e76  mov     [rbp+120h+var_150], rax
0x140001e7a  mov     rax, [rbp+120h+arg_58]
0x140001e81  mov     [rbp+120h+var_160], rax
0x140001e85  mov     [rbp+120h+var_70], rcx
0x140001e8c  mov     [rbp+120h+var_F8], 4
0x140001e94  mov     [rbp+120h+var_108], 4
0x140001e9c  mov     [rbp+120h+var_118], 4
0x140001ea4  mov     [rbp+120h+var_128], 4
0x140001eac  mov     [rbp+120h+var_138], 8
0x140001eb4  mov     [rbp+120h+var_148], 8
0x140001ebc  mov     [rbp+120h+var_158], 8
0x140001ec4  mov     rax, [rbp+120h+arg_50]
0x140001ecb  mov     [rbp+120h+var_170], rax
0x140001ecf  mov     rax, [rbp+120h+arg_48]
0x140001ed6  mov     [rbp+120h+var_180], rax
0x140001eda  mov     rax, [rbp+120h+arg_40]
0x140001ee1  mov     [rbp+120h+var_190], rax
0x140001ee5  mov     rax, [rbp+120h+arg_38]
0x140001eec  mov     [rbp+120h+var_1A0], rax
0x140001ef0  mov     rax, [rbp+120h+arg_30]
0x140001ef7  mov     [rsp+220h+var_1B0], rax
0x140001efc  mov     rax, [rbp+120h+arg_28]
0x140001f03  mov     [rbp+120h+var_168], 8
0x140001f0b  mov     [rbp+120h+var_178], 4
0x140001f13  mov     [rbp+120h+var_188], 4
0x140001f1b  mov     rcx, [rax]
0x140001f1e  mov     [rbp+120h+var_198], 4
0x140001f26  mov     [rsp+220h+var_1A8], 4
0x140001f2f  test    rcx, rcx
0x140001f32  jz      short loc_140001F4B
0x140001f34  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001f38  inc     rax
0x140001f3b  cmp     [rcx+rax*2], r8w
0x140001f40  jnz     short loc_140001F38
0x140001f42  lea     edx, ds:2[rax*2]
0x140001f49  jmp     short loc_140001F52
0x140001f4b  lea     rcx, String
0x140001f52  mov     rax, [rbp+120h+arg_20]
0x140001f59  xor     r9d, r9d
0x140001f5c  mov     [rsp+220h+var_1D0], rax
0x140001f61  lea     rax, [rsp+220h+var_1F0]
0x140001f66  mov     [rsp+220h+var_1C0], rcx
0x140001f6b  mov     rcx, r10
0x140001f6e  mov     [rsp+220h+var_1B8], edx
0x140001f72  mov     rdx, r11
0x140001f75  mov     [rsp+220h+var_1F8], rax
0x140001f7a  mov     [rsp+220h+var_200], 1Eh
0x140001f82  mov     [rsp+220h+var_1B4], r8d
0x140001f87  mov     [rsp+220h+var_1C8], 8
0x140001f90  call    _tlgWriteTransfer_EventWriteTransfer
0x140001f95  mov     rcx, [rbp+120h+var_10]
0x140001f9c  xor     rcx, rsp; StackCookie
0x140001f9f  call    __security_check_cookie
0x140001fa4  add     rsp, 220h
0x140001fab  pop     rbp
0x140001fac  retn
```
