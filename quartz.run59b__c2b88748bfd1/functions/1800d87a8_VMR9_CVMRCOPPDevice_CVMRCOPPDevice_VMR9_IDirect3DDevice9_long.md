# VMR9::CVMRCOPPDevice::CVMRCOPPDevice(VMR9::IDirect3DDevice9 *,long *)

- ea: `0x1800d87a8`
- end: `0x1800d8a9a`
- name: `??0CVMRCOPPDevice@VMR9@@QEAA@PEAUIDirect3DDevice9@1@PEAJ@Z`
- size: `754`
- prototype: `_QWORD(VMR9::CVMRCOPPDevice *__hidden this, struct IDirect3DDevice9 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x1800d52f0`

## callees

- `0x18002d864`
- `0x1800388a0`
- `0x1800d870c`
- `0x1800d87a8`
- `0x1800e8164`
- `0x18015e010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800d8a60`
- `KERNEL32!FreeLibrary` at `0x18015cd35`
- `KERNEL32!FreeLibrary` at `0x1800d8a60`
- `KERNEL32!FreeLibrary` at `0x18015cd35`
- `ole32!CoTaskMemFree` at `0x1800d8a29`
- `ole32!CoTaskMemFree` at `0x18015ccf3`
- `ole32!CoTaskMemFree` at `0x1800d8a29`
- `ole32!CoTaskMemFree` at `0x18015ccf3`

## string_xrefs

- `0x1800d8846`: `DXVA2.DLL`

## pseudocode

```c
VMR9::CVMRCOPPDevice *__fastcall VMR9::CVMRCOPPDevice::CVMRCOPPDevice(
        VMR9::CVMRCOPPDevice *this,
        struct IDirect3DDevice9 *a2,
        int *a3)
{
  _QWORD *v5; // r12
  _QWORD *v6; // r13
  HMODULE *v7; // r14
  _DWORD *v8; // r15
  int IsCurrentVideoDriverAnLDDMDriver; // ebx
  __int64 v10; // rcx
  __int64 i; // rsi
  unsigned int v13; // [rsp+54h] [rbp-D4h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-D0h] BYREF
  struct IDirect3DDevice9 v15; // [rsp+60h] [rbp-C8h] BYREF
  int *v16; // [rsp+68h] [rbp-C0h]
  int *v17; // [rsp+70h] [rbp-B8h]
  VMR9::CVMRCOPPDevice *v18; // [rsp+78h] [rbp-B0h]
  __int64 v19; // [rsp+80h] [rbp-A8h] BYREF
  int v20; // [rsp+88h] [rbp-A0h]
  GUID v21; // [rsp+90h] [rbp-98h] BYREF
  __int128 v22; // [rsp+A0h] [rbp-88h] BYREF
  int v23; // [rsp+B0h] [rbp-78h]
  char v24[48]; // [rsp+B8h] [rbp-70h] BYREF

  v16 = a3;
  v18 = this;
  v17 = a3;
  *(_QWORD *)this = 0;
  v5 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  v6 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  v7 = (HMODULE *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v8 = (_DWORD *)((char *)this + 36);
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 8) = 0;
  LODWORD(v15.lpVtbl) = 1;
  v13 = 0;
  pv = 0;
  IsCurrentVideoDriverAnLDDMDriver = VMR9::IsCurrentVideoDriverAnLDDMDriver((VMR9 *)a2, &v15, a3);
  if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
  {
    if ( LODWORD(v15.lpVtbl) )
    {
      v22 = *(_OWORD *)L"DXVA2.DLL";
      v23 = *(_DWORD *)L"L";
      strcpy(v24, "OPMGetVideoOutputsFromIDirect3DDevice9Object");
      v15.lpVtbl = 0;
      IsCurrentVideoDriverAnLDDMDriver = VMR9::LoadDLLAndGetFunctionPointer<long (*)(VMR9::IDirect3DDevice9 *,enum VMR9::_OPM_VIDEO_OUTPUT_SEMANTICS,unsigned long *,VMR9::IOPMVideoOutput * * *)>(
                                           &v22,
                                           v24,
                                           v7,
                                           &v15);
      if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
      {
        IsCurrentVideoDriverAnLDDMDriver = ((__int64 (__fastcall *)(struct IDirect3DDevice9 *, _QWORD, unsigned int *, LPVOID *))v15.lpVtbl)(
                                             a2,
                                             0,
                                             &v13,
                                             &pv);
        if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
        {
          if ( v13 == 1 )
          {
            v10 = *(_QWORD *)pv;
            *v6 = *(_QWORD *)pv;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
            *((_DWORD *)this + 8) = 4;
          }
          else
          {
            IsCurrentVideoDriverAnLDDMDriver = -2147467259;
          }
        }
      }
    }
    else
    {
      IsCurrentVideoDriverAnLDDMDriver = ((__int64 (__fastcall *)(struct IDirect3DDevice9 *, GUID *, VMR9::CVMRCOPPDevice *))a2->lpVtbl->QueryInterface)(
                                           a2,
                                           &IID_IDirect3DVideoDevice9,
                                           this);
      if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
      {
        v19 = 0;
        v20 = 0;
        v21 = DXVA_COPPDevice;
        IsCurrentVideoDriverAnLDDMDriver = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *, _QWORD, _DWORD, _QWORD *))(**(_QWORD **)this + 64LL))(
                                             *(_QWORD *)this,
                                             &v21,
                                             &v19,
                                             0,
                                             0,
                                             v5);
        if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
        {
          IsCurrentVideoDriverAnLDDMDriver = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v5 + 40LL))(
                                               *v5,
                                               1,
                                               0);
          if ( IsCurrentVideoDriverAnLDDMDriver >= 0 )
          {
            if ( !*v8 )
              IsCurrentVideoDriverAnLDDMDriver = -2147418113;
            if ( !IsCurrentVideoDriverAnLDDMDriver )
              *((_DWORD *)this + 8) = 1;
          }
        }
      }
    }
  }
  for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
    RELEASE<IDDVideoAcceleratorContainer>((char *)pv + 8 * i);
  CoTaskMemFree(pv);
  if ( IsCurrentVideoDriverAnLDDMDriver )
  {
    *v16 = IsCurrentVideoDriverAnLDDMDriver;
    RELEASE<IDDVideoAcceleratorContainer>(v5);
    RELEASE<IDDVideoAcceleratorContainer>(this);
    RELEASE<IDDVideoAcceleratorContainer>(v6);
    if ( *v7 )
    {
      FreeLibrary(*v7);
      *v7 = 0;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800d87a8  push    rbx
0x1800d87aa  push    rsi
0x1800d87ab  push    rdi
0x1800d87ac  push    r12
0x1800d87ae  push    r13
0x1800d87b0  push    r14
0x1800d87b2  push    r15
0x1800d87b4  sub     rsp, 0F0h
0x1800d87bb  mov     rax, cs:__security_cookie
0x1800d87c2  xor     rax, rsp
0x1800d87c5  mov     [rsp+128h+var_40], rax
0x1800d87cd  mov     rax, r8
0x1800d87d0  mov     [rsp+128h+var_C0], rax
0x1800d87d5  mov     rsi, rdx
0x1800d87d8  mov     rdi, rcx
0x1800d87db  mov     [rsp+128h+var_B0], rcx
0x1800d87e0  mov     [rsp+128h+var_B8], rax
0x1800d87e5  xor     eax, eax
0x1800d87e7  mov     [rcx], rax
0x1800d87ea  lea     r12, [rcx+8]
0x1800d87ee  mov     [r12], rax
0x1800d87f2  lea     r13, [rcx+10h]
0x1800d87f6  mov     [r13+0], rax
0x1800d87fa  lea     r14, [rcx+18h]
0x1800d87fe  mov     [r14], rax
0x1800d8801  lea     r15, [rcx+24h]
0x1800d8805  mov     [r15], eax
0x1800d8808  mov     [rcx+20h], eax
0x1800d880b  mov     [rsp+128h+var_D8], eax
0x1800d880f  mov     dword ptr [rsp+128h+var_C8.lpVtbl], 1
0x1800d8817  mov     [rsp+128h+var_D4], eax
0x1800d881b  mov     [rsp+128h+pv], rax
0x1800d8820  lea     rdx, [rsp+128h+var_C8]; struct IDirect3DDevice9 *
0x1800d8825  mov     rcx, rsi; this
0x1800d8828  call    ?IsCurrentVideoDriverAnLDDMDriver@VMR9@@YAJPEAUIDirect3DDevice9@1@PEAH@Z; VMR9::IsCurrentVideoDriverAnLDDMDriver(VMR9::IDirect3DDevice9 *,int *)
0x1800d882d  mov     ebx, eax
0x1800d882f  mov     [rsp+128h+var_D8], eax
0x1800d8833  test    eax, eax
0x1800d8835  js      loc_1800D8A06
0x1800d883b  cmp     dword ptr [rsp+128h+var_C8.lpVtbl], 0
0x1800d8840  jz      loc_1800D8923
0x1800d8846  movups  xmm0, xmmword ptr cs:aDxva2Dll; "DXVA2.DLL"
0x1800d884d  movups  [rsp+128h+var_88], xmm0
0x1800d8855  mov     eax, dword ptr cs:aDxva2Dll+10h; "L"
0x1800d885b  mov     [rsp+128h+var_78], eax
0x1800d8862  movups  xmm0, xmmword ptr cs:aOpmgetvideoout_0; "OPMGetVideoOutputsFromIDirect3DDevice9O"...
0x1800d8869  movups  xmmword ptr [rsp+128h+var_70], xmm0
0x1800d8871  movups  xmm1, xmmword ptr cs:aOpmgetvideoout_0+10h; "tsFromIDirect3DDevice9Object"
0x1800d8878  movups  xmmword ptr [rsp+128h+var_70+10h], xmm1
0x1800d8880  movups  xmm0, xmmword ptr cs:aOpmgetvideoout_0+1Dh; "3DDevice9Object"
0x1800d8887  movups  xmmword ptr [rsp+128h+var_70+1Dh], xmm0
0x1800d888f  mov     [rsp+128h+var_C8.lpVtbl], 0
0x1800d8898  lea     r9, [rsp+128h+var_C8]
0x1800d889d  mov     r8, r14
0x1800d88a0  lea     rdx, [rsp+128h+var_70]
0x1800d88a8  lea     rcx, [rsp+128h+var_88]
0x1800d88b0  call    ??$LoadDLLAndGetFunctionPointer@P6AJPEAUIDirect3DDevice9@VMR9@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@2@PEAKPEAPEAPEAUIOPMVideoOutput@2@@Z@VMR9@@YAJPEBGPEBDPEAPEAUHINSTANCE__@@PEAP6AJPEAUIDirect3DDevice9@0@W4_OPM_VIDEO_OUTPUT_SEMANTICS@0@PEAKPEAPEAPEAUIOPMVideoOutput@0@@Z@Z; VMR9::LoadDLLAndGetFunctionPointer<long (*)(VMR9::IDirect3DDevice9 *,VMR9::_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,VMR9::IOPMVideoOutput * * *)>(ushort const *,char const *,HINSTANCE__ * *,long (**)(VMR9::IDirect3DDevice9 *,VMR9::_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,VMR9::IOPMVideoOutput * * *))
0x1800d88b5  mov     ebx, eax
0x1800d88b7  mov     [rsp+128h+var_D8], eax
0x1800d88bb  test    eax, eax
0x1800d88bd  js      loc_1800D8A06
0x1800d88c3  lea     r9, [rsp+128h+pv]
0x1800d88c8  lea     r8, [rsp+128h+var_D4]
0x1800d88cd  xor     edx, edx
0x1800d88cf  mov     rcx, rsi
0x1800d88d2  mov     rax, [rsp+128h+var_C8.lpVtbl]
0x1800d88d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d88dc  mov     ebx, eax
0x1800d88de  mov     [rsp+128h+var_D8], eax
0x1800d88e2  test    eax, eax
0x1800d88e4  js      loc_1800D8A06
0x1800d88ea  cmp     [rsp+128h+var_D4], 1
0x1800d88ef  jz      short loc_1800D88FF
0x1800d88f1  mov     ebx, 80004005h
0x1800d88f6  mov     [rsp+128h+var_D8], ebx
0x1800d88fa  jmp     loc_1800D8A06
0x1800d88ff  mov     rax, [rsp+128h+pv]
0x1800d8904  mov     rcx, [rax]
0x1800d8907  mov     [r13+0], rcx
0x1800d890b  mov     rax, [rcx]
0x1800d890e  mov     rax, [rax+8]
0x1800d8912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8917  mov     dword ptr [rdi+20h], 4
0x1800d891e  jmp     loc_1800D8A06
0x1800d8923  mov     rax, [rsi]
0x1800d8926  mov     r8, rdi
0x1800d8929  lea     rdx, IID_IDirect3DVideoDevice9
0x1800d8930  mov     rcx, rsi
0x1800d8933  mov     rax, [rax]
0x1800d8936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d893b  mov     ebx, eax
0x1800d893d  mov     [rsp+128h+var_D8], eax
0x1800d8941  test    eax, eax
0x1800d8943  js      loc_1800D8A06
0x1800d8949  mov     [rsp+128h+var_A8], 0
0x1800d8955  mov     [rsp+128h+var_A0], 0
0x1800d8960  movups  xmm0, xmmword ptr cs:DXVA_COPPDevice.Data1
0x1800d8967  movdqu  [rsp+128h+var_98], xmm0
0x1800d8970  mov     rcx, [rdi]
0x1800d8973  mov     rax, [rcx]
0x1800d8976  mov     [rsp+128h+var_100], r12
0x1800d897b  mov     dword ptr [rsp+128h+var_108], 0
0x1800d8983  xor     r9d, r9d
0x1800d8986  lea     r8, [rsp+128h+var_A8]
0x1800d898e  lea     rdx, [rsp+128h+var_98]
0x1800d8996  mov     rax, [rax+40h]
0x1800d899a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d899f  mov     ebx, eax
0x1800d89a1  mov     [rsp+128h+var_D8], eax
0x1800d89a5  test    eax, eax
0x1800d89a7  js      short loc_1800D8A06
0x1800d89a9  mov     rcx, [r12]
0x1800d89ad  mov     rax, [rcx]
0x1800d89b0  mov     [rsp+128h+var_F0], 0
0x1800d89b9  mov     [rsp+128h+var_F8], 0
0x1800d89c1  mov     dword ptr [rsp+128h+var_100], 4
0x1800d89c9  mov     [rsp+128h+var_108], r15
0x1800d89ce  xor     r9d, r9d
0x1800d89d1  xor     r8d, r8d
0x1800d89d4  lea     edx, [r9+1]
0x1800d89d8  mov     rax, [rax+28h]
0x1800d89dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d89e1  mov     ebx, eax
0x1800d89e3  mov     [rsp+128h+var_D8], eax
0x1800d89e7  test    eax, eax
0x1800d89e9  js      short loc_1800D8A06
0x1800d89eb  mov     eax, 8000FFFFh
0x1800d89f0  cmp     dword ptr [r15], 0
0x1800d89f4  cmovz   ebx, eax
0x1800d89f7  mov     [rsp+128h+var_D8], ebx
0x1800d89fb  test    ebx, ebx
0x1800d89fd  jnz     short loc_1800D8A06
0x1800d89ff  mov     dword ptr [rdi+20h], 1
0x1800d8a06  xor     esi, esi
0x1800d8a08  cmp     [rsp+128h+var_D4], esi
0x1800d8a0c  jbe     short loc_1800D8A24
0x1800d8a0e  mov     rax, [rsp+128h+pv]
0x1800d8a13  lea     rcx, [rax+rsi*8]
0x1800d8a17  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800d8a1c  inc     esi
0x1800d8a1e  cmp     esi, [rsp+128h+var_D4]
0x1800d8a22  jb      short loc_1800D8A0E
0x1800d8a24  mov     rcx, [rsp+128h+pv]; pv
0x1800d8a29  call    cs:__imp_CoTaskMemFree
0x1800d8a30  nop     dword ptr [rax+rax+00h]
0x1800d8a35  test    ebx, ebx
0x1800d8a37  jz      short loc_1800D8A73
0x1800d8a39  mov     rax, [rsp+128h+var_C0]
0x1800d8a3e  mov     [rax], ebx
0x1800d8a40  mov     rcx, r12
0x1800d8a43  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800d8a48  mov     rcx, rdi
0x1800d8a4b  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800d8a50  mov     rcx, r13
0x1800d8a53  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800d8a58  mov     rcx, [r14]; hLibModule
0x1800d8a5b  test    rcx, rcx
0x1800d8a5e  jz      short loc_1800D8A73
0x1800d8a60  call    cs:__imp_FreeLibrary
0x1800d8a67  nop     dword ptr [rax+rax+00h]
0x1800d8a6c  mov     qword ptr [r14], 0
0x1800d8a73  mov     rax, rdi
0x1800d8a76  mov     rcx, [rsp+128h+var_40]
0x1800d8a7e  xor     rcx, rsp; StackCookie
0x1800d8a81  call    __security_check_cookie
0x1800d8a86  add     rsp, 0F0h
0x1800d8a8d  pop     r15
0x1800d8a8f  pop     r14
0x1800d8a91  pop     r13
0x1800d8a93  pop     r12
0x1800d8a95  pop     rdi
0x1800d8a96  pop     rsi
0x1800d8a97  pop     rbx
0x1800d8a98  retn
0x18015ccca  push    rbx
0x18015cccc  push    rbp
0x18015cccd  sub     rsp, 58h
0x18015ccd1  mov     rbp, rdx
0x18015ccd4  xor     ebx, ebx
0x18015ccd6  cmp     [rbp+54h], ebx
0x18015ccd9  jbe     short loc_18015CCEF
0x18015ccdb  mov     rax, [rbp+58h]
0x18015ccdf  lea     rcx, [rax+rbx*8]
0x18015cce3  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015cce8  inc     ebx
0x18015ccea  cmp     ebx, [rbp+54h]
0x18015cced  jb      short loc_18015CCDB
0x18015ccef  mov     rcx, [rbp+58h]; pv
0x18015ccf3  call    cs:__imp_CoTaskMemFree
0x18015ccfa  nop     dword ptr [rax+rax+00h]
0x18015ccff  mov     ecx, [rbp+50h]
0x18015cd02  test    ecx, ecx
0x18015cd04  jz      short loc_18015CD49
0x18015cd06  mov     rax, [rbp+70h]
0x18015cd0a  mov     [rax], ecx
0x18015cd0c  mov     rbx, [rbp+78h]
0x18015cd10  lea     rcx, [rbx+8]
0x18015cd14  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015cd19  mov     rcx, rbx
0x18015cd1c  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015cd21  lea     rcx, [rbx+10h]
0x18015cd25  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015cd2a  cmp     qword ptr [rbx+18h], 0
0x18015cd2f  jz      short loc_18015CD49
0x18015cd31  mov     rcx, [rbx+18h]; hLibModule
0x18015cd35  call    cs:__imp_FreeLibrary
0x18015cd3c  nop     dword ptr [rax+rax+00h]
0x18015cd41  mov     qword ptr [rbx+18h], 0
0x18015cd49  add     rsp, 58h
0x18015cd4d  pop     rbp
0x18015cd4e  pop     rbx
0x18015cd4f  retn
```
