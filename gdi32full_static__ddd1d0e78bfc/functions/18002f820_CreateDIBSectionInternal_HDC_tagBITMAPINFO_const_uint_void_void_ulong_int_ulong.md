# CreateDIBSectionInternal(HDC__ *,tagBITMAPINFO const *,uint,void * *,void *,ulong,int,ulong)

- ea: `0x18002f820`
- end: `0x18002fb5f`
- name: `?CreateDIBSectionInternal@@YAPEAUHBITMAP__@@PEAUHDC__@@PEBUtagBITMAPINFO@@IPEAPEAXPEAXKHK@Z`
- size: `831`
- prototype: `HBITMAP __fastcall(HDC, const struct tagBITMAPINFO *, unsigned int, void **, void *, unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e290`
- `0x18002f1f0`
- `0x18002f7e0`

## callees

- `0x18002f820`
- `0x180036734`
- `0x18003888c`
- `0x180039ea4`
- `0x180039fa0`
- `0x18003a1e4`
- `0x18003ae00`
- `0x180049e34`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x18002fa76`
- `GDI32!GdiSetLastError` at `0x18002fa76`
- `ntdll!RtlFreeHeap` at `0x18002f9b6`
- `ntdll!RtlFreeHeap` at `0x18002f9db`
- `ntdll!RtlFreeHeap` at `0x18002fb4e`
- `ntdll!RtlFreeHeap` at `0x18002f9b6`
- `ntdll!RtlFreeHeap` at `0x18002f9db`
- `ntdll!RtlFreeHeap` at `0x18002fb4e`
- `win32u!NtGdiCreateSessionMappedDIBSection` at `0x18002fb02`
- `win32u!NtGdiCreateSessionMappedDIBSection` at `0x18002fb02`
- `win32u!NtGdiCreateDIBSection` at `0x18002fa2f`
- `win32u!NtGdiCreateDIBSection` at `0x18002fa2f`

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
0x18002f820  push    rbp
0x18002f822  push    rbx
0x18002f823  push    rsi
0x18002f824  push    rdi
0x18002f825  push    r12
0x18002f827  push    r13
0x18002f829  push    r14
0x18002f82b  push    r15
0x18002f82d  lea     rbp, [rsp-218h]
0x18002f835  sub     rsp, 318h
0x18002f83c  mov     rax, cs:__security_cookie
0x18002f843  xor     rax, rsp
0x18002f846  mov     [rbp+250h+var_50], rax
0x18002f84d  mov     r13d, [rbp+250h+arg_28]
0x18002f854  mov     eax, r8d
0x18002f857  mov     r12, [rbp+250h+arg_20]
0x18002f85e  lea     r8, [rsp+350h+var_300]
0x18002f863  mov     r15, rcx
0x18002f866  mov     [rsp+350h+var_2E0], rcx
0x18002f86b  mov     ecx, [rbp+250h+arg_38]
0x18002f871  mov     rsi, rdx
0x18002f874  mov     [rbp+250h+var_2D0], ecx
0x18002f877  mov     r14, r9
0x18002f87a  mov     [rsp+350h+var_2E8], rdx
0x18002f87f  mov     rcx, rsi
0x18002f882  xor     r9d, r9d
0x18002f885  mov     [rsp+350h+var_2F4], eax
0x18002f889  mov     edx, eax
0x18002f88b  mov     [rsp+350h+var_2F8], r13d
0x18002f890  mov     [rsp+350h+var_2D8], 0
0x18002f899  mov     [rsp+350h+var_300], 0
0x18002f8a1  call    pbmiConvertInfo
0x18002f8a6  mov     rbx, rax
0x18002f8a9  test    rax, rax
0x18002f8ac  jz      short loc_18002F8B7
0x18002f8ae  cmp     dword ptr [rax], 28h ; '('
0x18002f8b1  jnb     loc_18002FA62
0x18002f8b7  cmp     [rbp+250h+arg_30], 0
0x18002f8be  jnz     loc_18002FB13
0x18002f8c4  xor     edi, edi
0x18002f8c6  test    rbx, rbx
0x18002f8c9  jz      loc_18002FA9B
0x18002f8cf  test    r12, r12
0x18002f8d2  jnz     loc_18002FADD
0x18002f8d8  xor     esi, esi
0x18002f8da  lea     rcx, [rbp+250h+var_2A0]; void *
0x18002f8de  xor     edx, edx; Val
0x18002f8e0  mov     [rsp+350h+var_2F0], esi
0x18002f8e4  mov     r8d, 24Ch; Size
0x18002f8ea  call    memset_0
0x18002f8ef  xorps   xmm0, xmm0
0x18002f8f2  mov     [rsp+350h+var_2FC], edi
0x18002f8f6  xor     eax, eax
0x18002f8f8  lea     r9, [rsp+350h+var_2FC]
0x18002f8fd  lea     r8, [rbp+250h+var_2B8]
0x18002f901  mov     [rbp+250h+var_2A8], rax
0x18002f905  lea     rdx, [rbp+250h+var_2A0]
0x18002f909  mov     rcx, rbx
0x18002f90c  movups  [rbp+250h+var_2B8], xmm0
0x18002f910  call    IcmGetBitmapColorSpace
0x18002f915  test    eax, eax
0x18002f917  jz      loc_18002F9F1
0x18002f91d  lea     rcx, [rbp+250h+P]
0x18002f921  mov     [rbp+250h+P], rdi
0x18002f925  mov     [rbp+250h+var_2C8], rdi
0x18002f929  call    IcmGetDefaultCamp
0x18002f92e  mov     ecx, [rbp+250h+var_290]
0x18002f931  lea     rdx, [rbp+250h+var_2C8]
0x18002f935  call    IcmGetDefaultGmmp
0x18002f93a  mov     rdi, [rbp+250h+P]
0x18002f93e  lea     r8, [rbp+250h+var_2B8]
0x18002f942  mov     r13d, [rsp+350h+var_2FC]
0x18002f947  lea     rdx, [rbp+250h+var_2A0]
0x18002f94b  mov     r15, [rbp+250h+var_2C8]
0x18002f94f  mov     r9, rdi
0x18002f952  mov     rcx, [rsp+350h+var_2E0]
0x18002f957  mov     [rsp+350h+var_328], r13d
0x18002f95c  mov     [rsp+350h+var_330], r15
0x18002f961  call    IcmGetColorSpaceByColorSpace
0x18002f966  mov     rsi, rax
0x18002f969  test    rax, rax
0x18002f96c  jnz     short loc_18002F99F
0x18002f96e  mov     rcx, [rsp+350h+var_2E0]
0x18002f973  lea     r8, [rbp+250h+var_2B8]
0x18002f977  or      r13d, 10010h
0x18002f97e  mov     [rsp+350h+var_2F0], 1
0x18002f986  mov     [rsp+350h+var_328], r13d
0x18002f98b  lea     rdx, [rbp+250h+var_2A0]
0x18002f98f  mov     r9, rdi
0x18002f992  mov     [rsp+350h+var_330], r15
0x18002f997  call    IcmCreateColorSpaceByColorSpace
0x18002f99c  mov     rsi, rax
0x18002f99f  test    rdi, rdi
0x18002f9a2  jz      short loc_18002F9C2
0x18002f9a4  mov     rcx, gs:60h
0x18002f9ad  mov     r8, rdi; P
0x18002f9b0  xor     edx, edx; Flags
0x18002f9b2  mov     rcx, [rcx+30h]; HeapHandle
0x18002f9b6  call    cs:__imp_RtlFreeHeap
0x18002f9bd  nop     dword ptr [rax+rax+00h]
0x18002f9c2  xor     edi, edi
0x18002f9c4  test    r15, r15
0x18002f9c7  jz      short loc_18002F9E7
0x18002f9c9  mov     rcx, gs:60h
0x18002f9d2  mov     r8, r15; P
0x18002f9d5  xor     edx, edx; Flags
0x18002f9d7  mov     rcx, [rcx+30h]; HeapHandle
0x18002f9db  call    cs:__imp_RtlFreeHeap
0x18002f9e2  nop     dword ptr [rax+rax+00h]
0x18002f9e7  mov     r13d, [rsp+350h+var_2F8]
0x18002f9ec  mov     r15, [rsp+350h+var_2E0]
0x18002f9f1  mov     r9, rbx
0x18002f9f4  mov     r8d, r13d
0x18002f9f7  mov     rdx, r12
0x18002f9fa  mov     rcx, r15
0x18002f9fd  cmp     [rbp+250h+arg_30], edi
0x18002fa03  jnz     loc_18002FAE9
0x18002fa09  lea     rax, [rsp+350h+var_2D8]
0x18002fa0e  mov     [rsp+350h+var_310], rax
0x18002fa13  mov     eax, [rbp+250h+var_2D0]
0x18002fa16  mov     [rsp+350h+var_318], rsi
0x18002fa1b  mov     [rsp+350h+var_320], eax
0x18002fa1f  mov     eax, [rsp+350h+var_300]
0x18002fa23  mov     [rsp+350h+var_328], eax
0x18002fa27  mov     eax, [rsp+350h+var_2F4]
0x18002fa2b  mov     dword ptr [rsp+350h+var_330], eax
0x18002fa2f  call    cs:__imp_NtGdiCreateDIBSection
0x18002fa36  nop     dword ptr [rax+rax+00h]
0x18002fa3b  mov     rdi, rax
0x18002fa3e  test    rax, rax
0x18002fa41  jz      short loc_18002FA86
0x18002fa43  test    r14, r14
0x18002fa46  jz      short loc_18002FA50
0x18002fa48  cmp     [rsp+350h+var_2D8], 0
0x18002fa4e  jz      short loc_18002FA86
0x18002fa50  test    rsi, rsi
0x18002fa53  jz      short loc_18002FA96
0x18002fa55  cmp     [rsp+350h+var_2F0], 0
0x18002fa5a  jz      short loc_18002FA96
0x18002fa5c  mov     [rsi+10h], rdi
0x18002fa60  jmp     short loc_18002FA96
0x18002fa62  mov     ecx, [rax+10h]
0x18002fa65  sub     ecx, 4
0x18002fa68  cmp     ecx, 1
0x18002fa6b  ja      loc_18002F8B7
0x18002fa71  mov     ecx, 57h ; 'W'
0x18002fa76  call    cs:__imp_GdiSetLastError
0x18002fa7d  nop     dword ptr [rax+rax+00h]
0x18002fa82  xor     eax, eax
0x18002fa84  jmp     short loc_18002FAB9
0x18002fa86  xor     edi, edi
0x18002fa88  mov     [rsp+350h+var_2D8], rdi
0x18002fa8d  test    rsi, rsi
0x18002fa90  jnz     loc_18002FB2A
0x18002fa96  mov     rsi, [rsp+350h+var_2E8]
0x18002fa9b  test    r14, r14
0x18002fa9e  jz      short loc_18002FAA8
0x18002faa0  mov     rax, [rsp+350h+var_2D8]
0x18002faa5  mov     [r14], rax
0x18002faa8  test    rbx, rbx
0x18002faab  jz      short loc_18002FAB6
0x18002faad  cmp     rbx, rsi
0x18002fab0  jnz     loc_18002FB3C
0x18002fab6  mov     rax, rdi
0x18002fab9  mov     rcx, [rbp+250h+var_50]
0x18002fac0  xor     rcx, rsp; StackCookie
0x18002fac3  call    __security_check_cookie
0x18002fac8  add     rsp, 318h
0x18002facf  pop     r15
0x18002fad1  pop     r14
0x18002fad3  pop     r13
0x18002fad5  pop     r12
0x18002fad7  pop     rdi
0x18002fad8  pop     rsi
0x18002fad9  pop     rbx
0x18002fada  pop     rbp
0x18002fadb  retn
0x18002fadd  test    r13b, 3
0x18002fae1  jz      loc_18002F8D8
0x18002fae7  jmp     short loc_18002FA9B
0x18002fae9  mov     eax, [rsp+350h+var_300]
0x18002faed  mov     [rsp+350h+var_318], rsi
0x18002faf2  mov     [rsp+350h+var_320], edi
0x18002faf6  mov     [rsp+350h+var_328], eax
0x18002fafa  mov     eax, [rsp+350h+var_2F4]
0x18002fafe  mov     dword ptr [rsp+350h+var_330], eax
0x18002fb02  call    cs:__imp_NtGdiCreateSessionMappedDIBSection
0x18002fb09  nop     dword ptr [rax+rax+00h]
0x18002fb0e  jmp     loc_18002FA3B
0x18002fb13  test    r12, r12
0x18002fb16  jz      loc_18002FA71
0x18002fb1c  test    r14, r14
0x18002fb1f  jz      loc_18002F8C4
0x18002fb25  jmp     loc_18002FA71
0x18002fb2a  xor     r8d, r8d
0x18002fb2d  mov     rdx, rsi
0x18002fb30  xor     ecx, ecx
0x18002fb32  call    IcmReleaseColorSpace
0x18002fb37  jmp     loc_18002FA96
0x18002fb3c  mov     rcx, gs:60h
0x18002fb45  mov     r8, rbx; P
0x18002fb48  xor     edx, edx; Flags
0x18002fb4a  mov     rcx, [rcx+30h]; HeapHandle
0x18002fb4e  call    cs:__imp_RtlFreeHeap
0x18002fb55  nop     dword ptr [rax+rax+00h]
0x18002fb5a  jmp     loc_18002FAB6
```
