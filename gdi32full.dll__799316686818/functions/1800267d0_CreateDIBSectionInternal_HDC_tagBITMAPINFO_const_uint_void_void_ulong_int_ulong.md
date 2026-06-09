# CreateDIBSectionInternal(HDC__ *,tagBITMAPINFO const *,uint,void * *,void *,ulong,int,ulong)

- ea: `0x1800267d0`
- end: `0x180026ae6`
- name: `?CreateDIBSectionInternal@@YAPEAUHBITMAP__@@PEAUHDC__@@PEBUtagBITMAPINFO@@IPEAPEAXPEAXKHK@Z`
- size: `790`
- prototype: `HBITMAP __fastcall(HDC, const struct tagBITMAPINFO *, unsigned int, void **, void *, unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800251d0`
- `0x180026200`
- `0x180026790`

## callees

- `0x18001d4fc`
- `0x1800267d0`
- `0x180032a24`
- `0x180033ec8`
- `0x180033fb4`
- `0x1800341ec`
- `0x180034d98`
- `0x18003e5fc`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x180026a14`
- `GDI32!GdiSetLastError` at `0x180026a14`
- `ntdll!RtlFreeHeap` at `0x180026966`
- `ntdll!RtlFreeHeap` at `0x180026985`
- `ntdll!RtlFreeHeap` at `0x180026adb`
- `ntdll!RtlFreeHeap` at `0x180026966`
- `ntdll!RtlFreeHeap` at `0x180026985`
- `ntdll!RtlFreeHeap` at `0x180026adb`
- `win32u!NtGdiCreateSessionMappedDIBSection` at `0x180026a95`
- `win32u!NtGdiCreateSessionMappedDIBSection` at `0x180026a95`
- `win32u!NtGdiCreateDIBSection` at `0x1800269d3`
- `win32u!NtGdiCreateDIBSection` at `0x1800269d3`

## pseudocode

```c
__int64 __fastcall CreateDIBSectionInternal(
        HDC a1,
        const struct tagBITMAPINFO *a2,
        unsigned int a3,
        void **a4,
        void *a5,
        unsigned int a6,
        int a7,
        unsigned int a8)
{
  unsigned int v8; // r13d
  HDC v9; // r15
  const struct tagBITMAPINFO *v10; // rsi
  struct tagBITMAPINFO *v12; // rax
  struct tagBITMAPINFO *v13; // rbx
  __int64 v14; // rdi
  __int64 ColorSpaceByColorSpace; // rsi
  PVOID v16; // rdi
  int v17; // r13d
  PVOID v18; // r15
  __int64 SessionMappedDIBSection; // rax
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h]
  unsigned int v24; // [rsp+5Ch] [rbp-A4h]
  int v25; // [rsp+60h] [rbp-A0h]
  const struct tagBITMAPINFO *v26; // [rsp+68h] [rbp-98h]
  HDC v27; // [rsp+70h] [rbp-90h]
  void *v28; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v29; // [rsp+80h] [rbp-80h]
  PVOID v30; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+98h] [rbp-68h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-58h]
  _BYTE v34[16]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp-40h]

  v8 = a6;
  v9 = a1;
  v27 = a1;
  v10 = a2;
  v29 = a8;
  v26 = a2;
  v24 = a3;
  v23 = a6;
  v28 = 0;
  v21 = 0;
  v12 = (struct tagBITMAPINFO *)pbmiConvertInfo(a2, a3, &v21, 0);
  v13 = v12;
  if ( v12 && v12->bmiHeader.biSize >= 0x28 && v12->bmiHeader.biCompression - 4 <= 1 || a7 && (!a5 || a4) )
  {
    GdiSetLastError(87);
    return 0;
  }
  else
  {
    v14 = 0;
    if ( v12 && (!a5 || (a6 & 3) == 0) )
    {
      ColorSpaceByColorSpace = 0;
      v25 = 0;
      memset_0(v34, 0, 0x24Cu);
      v22 = 0;
      v33 = 0;
      v32 = 0;
      if ( (unsigned int)IcmGetBitmapColorSpace(v13, v34, &v32, &v22) )
      {
        P = 0;
        v30 = 0;
        IcmGetDefaultCamp(&P);
        IcmGetDefaultGmmp(v35, &v30);
        v16 = P;
        v17 = v22;
        v18 = v30;
        ColorSpaceByColorSpace = IcmGetColorSpaceByColorSpace(
                                   (_DWORD)v27,
                                   (unsigned int)v34,
                                   (unsigned int)&v32,
                                   (_DWORD)P,
                                   (__int64)v30,
                                   v22);
        if ( !ColorSpaceByColorSpace )
        {
          v25 = 1;
          ColorSpaceByColorSpace = IcmCreateColorSpaceByColorSpace(v27, v34, &v32, v16, v18, v17 | 0x10010u);
        }
        if ( v16 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
        if ( v18 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        v8 = v23;
        v9 = v27;
      }
      if ( a7 )
        SessionMappedDIBSection = NtGdiCreateSessionMappedDIBSection(
                                    v9,
                                    a5,
                                    v8,
                                    v13,
                                    v24,
                                    v21,
                                    0,
                                    ColorSpaceByColorSpace);
      else
        SessionMappedDIBSection = NtGdiCreateDIBSection(v9, a5, v8, v13, v24, v21, v29, ColorSpaceByColorSpace, &v28);
      v14 = SessionMappedDIBSection;
      if ( SessionMappedDIBSection && (!a4 || v28) )
      {
        if ( ColorSpaceByColorSpace && v25 )
          *(_QWORD *)(ColorSpaceByColorSpace + 16) = SessionMappedDIBSection;
      }
      else
      {
        v14 = 0;
        v28 = 0;
        if ( ColorSpaceByColorSpace )
          IcmReleaseColorSpace(0, ColorSpaceByColorSpace, 0);
      }
      v10 = v26;
    }
    if ( a4 )
      *a4 = v28;
    if ( v13 )
    {
      if ( v13 != v10 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x1800267d0  push    rbp
0x1800267d2  push    rbx
0x1800267d3  push    rsi
0x1800267d4  push    rdi
0x1800267d5  push    r12
0x1800267d7  push    r13
0x1800267d9  push    r14
0x1800267db  push    r15
0x1800267dd  lea     rbp, [rsp-218h]
0x1800267e5  sub     rsp, 318h
0x1800267ec  mov     rax, cs:__security_cookie
0x1800267f3  xor     rax, rsp
0x1800267f6  mov     [rbp+250h+var_50], rax
0x1800267fd  mov     r13d, [rbp+250h+arg_28]
0x180026804  mov     eax, r8d
0x180026807  mov     r12, [rbp+250h+arg_20]
0x18002680e  lea     r8, [rsp+350h+var_300]
0x180026813  mov     r15, rcx
0x180026816  mov     [rsp+350h+var_2E0], rcx
0x18002681b  mov     ecx, [rbp+250h+arg_38]
0x180026821  mov     rsi, rdx
0x180026824  mov     [rbp+250h+var_2D0], ecx
0x180026827  mov     r14, r9
0x18002682a  mov     [rsp+350h+var_2E8], rdx
0x18002682f  mov     rcx, rsi
0x180026832  xor     r9d, r9d
0x180026835  mov     [rsp+350h+var_2F4], eax
0x180026839  mov     edx, eax
0x18002683b  mov     [rsp+350h+var_2F8], r13d
0x180026840  mov     [rsp+350h+var_2D8], 0
0x180026849  mov     [rsp+350h+var_300], 0
0x180026851  call    pbmiConvertInfo
0x180026856  mov     rbx, rax
0x180026859  test    rax, rax
0x18002685c  jz      short loc_180026867
0x18002685e  cmp     dword ptr [rax], 28h ; '('
0x180026861  jnb     loc_180026A00
0x180026867  cmp     [rbp+250h+arg_30], 0
0x18002686e  jnz     loc_180026AA0
0x180026874  xor     edi, edi
0x180026876  test    rbx, rbx
0x180026879  jz      loc_180026A33
0x18002687f  test    r12, r12
0x180026882  jnz     loc_180026A70
0x180026888  xor     esi, esi
0x18002688a  lea     rcx, [rbp+250h+var_2A0]; void *
0x18002688e  xor     edx, edx; Val
0x180026890  mov     [rsp+350h+var_2F0], esi
0x180026894  mov     r8d, 24Ch; Size
0x18002689a  call    memset_0
0x18002689f  xorps   xmm0, xmm0
0x1800268a2  mov     [rsp+350h+var_2FC], edi
0x1800268a6  xor     eax, eax
0x1800268a8  lea     r9, [rsp+350h+var_2FC]
0x1800268ad  lea     r8, [rbp+250h+var_2B8]
0x1800268b1  mov     [rbp+250h+var_2A8], rax
0x1800268b5  lea     rdx, [rbp+250h+var_2A0]
0x1800268b9  mov     rcx, rbx
0x1800268bc  movups  [rbp+250h+var_2B8], xmm0
0x1800268c0  call    IcmGetBitmapColorSpace
0x1800268c5  test    eax, eax
0x1800268c7  jz      loc_180026995
0x1800268cd  lea     rcx, [rbp+250h+P]
0x1800268d1  mov     [rbp+250h+P], rdi
0x1800268d5  mov     [rbp+250h+var_2C8], rdi
0x1800268d9  call    IcmGetDefaultCamp
0x1800268de  mov     ecx, [rbp+250h+var_290]
0x1800268e1  lea     rdx, [rbp+250h+var_2C8]
0x1800268e5  call    IcmGetDefaultGmmp
0x1800268ea  mov     rdi, [rbp+250h+P]
0x1800268ee  lea     r8, [rbp+250h+var_2B8]
0x1800268f2  mov     r13d, [rsp+350h+var_2FC]
0x1800268f7  lea     rdx, [rbp+250h+var_2A0]
0x1800268fb  mov     r15, [rbp+250h+var_2C8]
0x1800268ff  mov     r9, rdi
0x180026902  mov     rcx, [rsp+350h+var_2E0]
0x180026907  mov     [rsp+350h+var_328], r13d
0x18002690c  mov     [rsp+350h+var_330], r15
0x180026911  call    IcmGetColorSpaceByColorSpace
0x180026916  mov     rsi, rax
0x180026919  test    rax, rax
0x18002691c  jnz     short loc_18002694F
0x18002691e  mov     rcx, [rsp+350h+var_2E0]
0x180026923  lea     r8, [rbp+250h+var_2B8]
0x180026927  or      r13d, 10010h
0x18002692e  mov     [rsp+350h+var_2F0], 1
0x180026936  mov     [rsp+350h+var_328], r13d
0x18002693b  lea     rdx, [rbp+250h+var_2A0]
0x18002693f  mov     r9, rdi
0x180026942  mov     [rsp+350h+var_330], r15
0x180026947  call    IcmCreateColorSpaceByColorSpace
0x18002694c  mov     rsi, rax
0x18002694f  test    rdi, rdi
0x180026952  jz      short loc_18002696C
0x180026954  mov     rcx, gs:60h
0x18002695d  mov     r8, rdi; P
0x180026960  xor     edx, edx; Flags
0x180026962  mov     rcx, [rcx+30h]; HeapHandle
0x180026966  call    cs:__imp_RtlFreeHeap
0x18002696c  xor     edi, edi
0x18002696e  test    r15, r15
0x180026971  jz      short loc_18002698B
0x180026973  mov     rcx, gs:60h
0x18002697c  mov     r8, r15; P
0x18002697f  xor     edx, edx; Flags
0x180026981  mov     rcx, [rcx+30h]; HeapHandle
0x180026985  call    cs:__imp_RtlFreeHeap
0x18002698b  mov     r13d, [rsp+350h+var_2F8]
0x180026990  mov     r15, [rsp+350h+var_2E0]
0x180026995  mov     r9, rbx
0x180026998  mov     r8d, r13d
0x18002699b  mov     rdx, r12
0x18002699e  mov     rcx, r15
0x1800269a1  cmp     [rbp+250h+arg_30], edi
0x1800269a7  jnz     loc_180026A7C
0x1800269ad  lea     rax, [rsp+350h+var_2D8]
0x1800269b2  mov     [rsp+350h+var_310], rax
0x1800269b7  mov     eax, [rbp+250h+var_2D0]
0x1800269ba  mov     [rsp+350h+var_318], rsi
0x1800269bf  mov     [rsp+350h+var_320], eax
0x1800269c3  mov     eax, [rsp+350h+var_300]
0x1800269c7  mov     [rsp+350h+var_328], eax
0x1800269cb  mov     eax, [rsp+350h+var_2F4]
0x1800269cf  mov     dword ptr [rsp+350h+var_330], eax
0x1800269d3  call    cs:__imp_NtGdiCreateDIBSection
0x1800269d9  mov     rdi, rax
0x1800269dc  test    rax, rax
0x1800269df  jz      short loc_180026A1E
0x1800269e1  test    r14, r14
0x1800269e4  jz      short loc_1800269EE
0x1800269e6  cmp     [rsp+350h+var_2D8], 0
0x1800269ec  jz      short loc_180026A1E
0x1800269ee  test    rsi, rsi
0x1800269f1  jz      short loc_180026A2E
0x1800269f3  cmp     [rsp+350h+var_2F0], 0
0x1800269f8  jz      short loc_180026A2E
0x1800269fa  mov     [rsi+10h], rdi
0x1800269fe  jmp     short loc_180026A2E
0x180026a00  mov     ecx, [rax+10h]
0x180026a03  sub     ecx, 4
0x180026a06  cmp     ecx, 1
0x180026a09  ja      loc_180026867
0x180026a0f  mov     ecx, 57h ; 'W'
0x180026a14  call    cs:__imp_GdiSetLastError
0x180026a1a  xor     eax, eax
0x180026a1c  jmp     short loc_180026A4D
0x180026a1e  xor     edi, edi
0x180026a20  mov     [rsp+350h+var_2D8], rdi
0x180026a25  test    rsi, rsi
0x180026a28  jnz     loc_180026AB7
0x180026a2e  mov     rsi, [rsp+350h+var_2E8]
0x180026a33  test    r14, r14
0x180026a36  jz      short loc_180026A40
0x180026a38  mov     rax, [rsp+350h+var_2D8]
0x180026a3d  mov     [r14], rax
0x180026a40  test    rbx, rbx
0x180026a43  jz      short loc_180026A4A
0x180026a45  cmp     rbx, rsi
0x180026a48  jnz     short loc_180026AC9
0x180026a4a  mov     rax, rdi
0x180026a4d  mov     rcx, [rbp+250h+var_50]
0x180026a54  xor     rcx, rsp; StackCookie
0x180026a57  call    __security_check_cookie
0x180026a5c  add     rsp, 318h
0x180026a63  pop     r15
0x180026a65  pop     r14
0x180026a67  pop     r13
0x180026a69  pop     r12
0x180026a6b  pop     rdi
0x180026a6c  pop     rsi
0x180026a6d  pop     rbx
0x180026a6e  pop     rbp
0x180026a6f  retn
0x180026a70  test    r13b, 3
0x180026a74  jz      loc_180026888
0x180026a7a  jmp     short loc_180026A33
0x180026a7c  mov     eax, [rsp+350h+var_300]
0x180026a80  mov     [rsp+350h+var_318], rsi
0x180026a85  mov     [rsp+350h+var_320], edi
0x180026a89  mov     [rsp+350h+var_328], eax
0x180026a8d  mov     eax, [rsp+350h+var_2F4]
0x180026a91  mov     dword ptr [rsp+350h+var_330], eax
0x180026a95  call    cs:__imp_NtGdiCreateSessionMappedDIBSection
0x180026a9b  jmp     loc_1800269D9
0x180026aa0  test    r12, r12
0x180026aa3  jz      loc_180026A0F
0x180026aa9  test    r14, r14
0x180026aac  jz      loc_180026874
0x180026ab2  jmp     loc_180026A0F
0x180026ab7  xor     r8d, r8d
0x180026aba  mov     rdx, rsi
0x180026abd  xor     ecx, ecx
0x180026abf  call    IcmReleaseColorSpace
0x180026ac4  jmp     loc_180026A2E
0x180026ac9  mov     rcx, gs:60h
0x180026ad2  mov     r8, rbx; P
0x180026ad5  xor     edx, edx; Flags
0x180026ad7  mov     rcx, [rcx+30h]; HeapHandle
0x180026adb  call    cs:__imp_RtlFreeHeap
0x180026ae1  jmp     loc_180026A4A
```
