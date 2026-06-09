# COPMVideoOutputWrapper::COPMVideoOutputWrapper(HMONITOR__ *,long *)

- ea: `0x1800b25c8`
- end: `0x1800b2748`
- name: `??0COPMVideoOutputWrapper@@QEAA@PEAUHMONITOR__@@PEAJ@Z`
- size: `384`
- prototype: `COPMVideoOutputWrapper *__fastcall(COPMVideoOutputWrapper *__hidden this, HMONITOR, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800af188`

## callees

- `0x18002d864`
- `0x1800388a0`
- `0x1800b2524`
- `0x1800b25c8`
- `0x18015e010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800b270f`
- `KERNEL32!FreeLibrary` at `0x18015c63a`
- `KERNEL32!FreeLibrary` at `0x1800b270f`
- `KERNEL32!FreeLibrary` at `0x18015c63a`
- `ole32!CoTaskMemFree` at `0x1800b26ef`
- `ole32!CoTaskMemFree` at `0x18015c610`
- `ole32!CoTaskMemFree` at `0x1800b26ef`
- `ole32!CoTaskMemFree` at `0x18015c610`

## string_xrefs

- `0x1800b2627`: `DXVA2.DLL`

## pseudocode

```c
COPMVideoOutputWrapper *__fastcall COPMVideoOutputWrapper::COPMVideoOutputWrapper(
        COPMVideoOutputWrapper *this,
        HMONITOR a2,
        int *a3)
{
  HMODULE *v6; // r14
  int Function; // ebx
  __int64 v8; // rcx
  __int64 i; // rsi
  unsigned int v11; // [rsp+30h] [rbp-98h] BYREF
  int v12; // [rsp+34h] [rbp-94h]
  LPVOID pv; // [rsp+38h] [rbp-90h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-88h] BYREF
  __int128 v15; // [rsp+58h] [rbp-70h] BYREF
  int v16; // [rsp+68h] [rbp-60h]
  char v17[32]; // [rsp+70h] [rbp-58h] BYREF

  v14[1] = this;
  v14[2] = a3;
  *(_QWORD *)this = 0;
  v6 = (HMODULE *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  v11 = 0;
  pv = 0;
  v15 = *(_OWORD *)L"DXVA2.DLL";
  v16 = *(_DWORD *)L"L";
  strcpy(v17, "OPMGetVideoOutputsFromHMONITOR");
  v14[0] = 0;
  Function = LoadDLLAndGetFunctionPointer<long (*)(HMONITOR__ *,enum _OPM_VIDEO_OUTPUT_SEMANTICS,unsigned long *,IOPMVideoOutput * * *)>(
               &v15,
               v17,
               (char *)this + 8,
               v14);
  v12 = Function;
  if ( Function >= 0 )
  {
    Function = ((__int64 (__fastcall *)(HMONITOR, _QWORD, unsigned int *, LPVOID *))v14[0])(a2, 0, &v11, &pv);
    v12 = Function;
    if ( Function >= 0 )
    {
      if ( v11 == 1 )
      {
        v8 = *(_QWORD *)pv;
        *(_QWORD *)this = *(_QWORD *)pv;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      }
      else
      {
        Function = -2147467259;
        v12 = -2147467259;
      }
    }
  }
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
    RELEASE<IDDVideoAcceleratorContainer>((char *)pv + 8 * i);
  CoTaskMemFree(pv);
  if ( Function )
  {
    RELEASE<IDDVideoAcceleratorContainer>(this);
    if ( *v6 )
    {
      FreeLibrary(*v6);
      *v6 = 0;
    }
    *a3 = Function;
  }
  return this;
}

```

## disassembly

```asm
0x1800b25c8  push    rbx
0x1800b25ca  push    rsi
0x1800b25cb  push    rdi
0x1800b25cc  push    r14
0x1800b25ce  push    r15
0x1800b25d0  sub     rsp, 0A0h
0x1800b25d7  mov     rax, cs:__security_cookie
0x1800b25de  xor     rax, rsp
0x1800b25e1  mov     [rsp+0C8h+var_38], rax
0x1800b25e9  mov     r15, r8
0x1800b25ec  mov     rsi, rdx
0x1800b25ef  mov     rdi, rcx
0x1800b25f2  mov     [rsp+0C8h+var_80], rcx
0x1800b25f7  mov     [rsp+0C8h+var_78], r8
0x1800b25fc  mov     qword ptr [rcx], 0
0x1800b2603  lea     r14, [rcx+8]
0x1800b2607  mov     qword ptr [r14], 0
0x1800b260e  mov     [rsp+0C8h+var_94], 80004005h
0x1800b2616  mov     [rsp+0C8h+var_98], 0
0x1800b261e  mov     [rsp+0C8h+pv], 0
0x1800b2627  movups  xmm0, xmmword ptr cs:aDxva2Dll; "DXVA2.DLL"
0x1800b262e  movups  [rsp+0C8h+var_70], xmm0
0x1800b2633  mov     eax, dword ptr cs:aDxva2Dll+10h; "L"
0x1800b2639  mov     [rsp+0C8h+var_60], eax
0x1800b263d  movups  xmm0, xmmword ptr cs:aOpmgetvideoout; "OPMGetVideoOutputsFromHMONITOR"
0x1800b2644  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x1800b2649  movups  xmm1, xmmword ptr cs:aOpmgetvideoout+0Fh; "utsFromHMONITOR"
0x1800b2650  movups  xmmword ptr [rsp+0C8h+var_58+0Fh], xmm1
0x1800b2655  mov     [rsp+0C8h+var_88], 0
0x1800b265e  lea     r9, [rsp+0C8h+var_88]
0x1800b2663  mov     r8, r14
0x1800b2666  lea     rdx, [rsp+0C8h+var_58]
0x1800b266b  lea     rcx, [rsp+0C8h+var_70]
0x1800b2670  call    ??$LoadDLLAndGetFunctionPointer@P6AJPEAUHMONITOR__@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@@PEAKPEAPEAPEAUIOPMVideoOutput@@@Z@@YAJPEBGPEBDPEAPEAUHINSTANCE__@@PEAP6AJPEAUHMONITOR__@@W4_OPM_VIDEO_OUTPUT_SEMANTICS@@PEAKPEAPEAPEAUIOPMVideoOutput@@@Z@Z; LoadDLLAndGetFunctionPointer<long (*)(HMONITOR__ *,_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,IOPMVideoOutput * * *)>(ushort const *,char const *,HINSTANCE__ * *,long (**)(HMONITOR__ *,_OPM_VIDEO_OUTPUT_SEMANTICS,ulong *,IOPMVideoOutput * * *))
0x1800b2675  mov     ebx, eax
0x1800b2677  mov     [rsp+0C8h+var_94], eax
0x1800b267b  test    eax, eax
0x1800b267d  js      short loc_1800B26CC
0x1800b267f  lea     r9, [rsp+0C8h+pv]
0x1800b2684  lea     r8, [rsp+0C8h+var_98]
0x1800b2689  xor     edx, edx
0x1800b268b  mov     rcx, rsi
0x1800b268e  mov     rax, [rsp+0C8h+var_88]
0x1800b2693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2698  mov     ebx, eax
0x1800b269a  mov     [rsp+0C8h+var_94], eax
0x1800b269e  test    eax, eax
0x1800b26a0  js      short loc_1800B26CC
0x1800b26a2  cmp     [rsp+0C8h+var_98], 1
0x1800b26a7  jz      short loc_1800B26B4
0x1800b26a9  mov     ebx, 80004005h
0x1800b26ae  mov     [rsp+0C8h+var_94], ebx
0x1800b26b2  jmp     short loc_1800B26CC
0x1800b26b4  mov     rax, [rsp+0C8h+pv]
0x1800b26b9  mov     rcx, [rax]
0x1800b26bc  mov     [rdi], rcx
0x1800b26bf  mov     rax, [rcx]
0x1800b26c2  mov     rax, [rax+8]
0x1800b26c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b26cb  nop
0x1800b26cc  xor     esi, esi
0x1800b26ce  cmp     [rsp+0C8h+var_98], esi
0x1800b26d2  jbe     short loc_1800B26EA
0x1800b26d4  mov     rax, [rsp+0C8h+pv]
0x1800b26d9  lea     rcx, [rax+rsi*8]
0x1800b26dd  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b26e2  inc     esi
0x1800b26e4  cmp     esi, [rsp+0C8h+var_98]
0x1800b26e8  jb      short loc_1800B26D4
0x1800b26ea  mov     rcx, [rsp+0C8h+pv]; pv
0x1800b26ef  call    cs:__imp_CoTaskMemFree
0x1800b26f6  nop     dword ptr [rax+rax+00h]
0x1800b26fb  test    ebx, ebx
0x1800b26fd  jz      short loc_1800B2725
0x1800b26ff  mov     rcx, rdi
0x1800b2702  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2707  mov     rcx, [r14]; hLibModule
0x1800b270a  test    rcx, rcx
0x1800b270d  jz      short loc_1800B2722
0x1800b270f  call    cs:__imp_FreeLibrary
0x1800b2716  nop     dword ptr [rax+rax+00h]
0x1800b271b  mov     qword ptr [r14], 0
0x1800b2722  mov     [r15], ebx
0x1800b2725  mov     rax, rdi
0x1800b2728  mov     rcx, [rsp+0C8h+var_38]
0x1800b2730  xor     rcx, rsp; StackCookie
0x1800b2733  call    __security_check_cookie
0x1800b2738  add     rsp, 0A0h
0x1800b273f  pop     r15
0x1800b2741  pop     r14
0x1800b2743  pop     rdi
0x1800b2744  pop     rsi
0x1800b2745  pop     rbx
0x1800b2746  retn
0x18015c5e6  push    rbx
0x18015c5e8  push    rbp
0x18015c5e9  push    rdi
0x18015c5ea  sub     rsp, 30h
0x18015c5ee  mov     rbp, rdx
0x18015c5f1  xor     ebx, ebx
0x18015c5f3  cmp     [rbp+30h], ebx
0x18015c5f6  jbe     short loc_18015C60C
0x18015c5f8  mov     rax, [rbp+38h]
0x18015c5fc  lea     rcx, [rax+rbx*8]
0x18015c600  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015c605  inc     ebx
0x18015c607  cmp     ebx, [rbp+30h]
0x18015c60a  jb      short loc_18015C5F8
0x18015c60c  mov     rcx, [rbp+38h]; pv
0x18015c610  call    cs:__imp_CoTaskMemFree
0x18015c617  nop     dword ptr [rax+rax+00h]
0x18015c61c  mov     edi, [rbp+34h]
0x18015c61f  test    edi, edi
0x18015c621  jz      short loc_18015C654
0x18015c623  mov     rbx, [rbp+48h]
0x18015c627  mov     rcx, rbx
0x18015c62a  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18015c62f  cmp     qword ptr [rbx+8], 0
0x18015c634  jz      short loc_18015C64E
0x18015c636  mov     rcx, [rbx+8]; hLibModule
0x18015c63a  call    cs:__imp_FreeLibrary
0x18015c641  nop     dword ptr [rax+rax+00h]
0x18015c646  mov     qword ptr [rbx+8], 0
0x18015c64e  mov     rax, [rbp+50h]
0x18015c652  mov     [rax], edi
0x18015c654  add     rsp, 30h
0x18015c658  pop     rdi
0x18015c659  pop     rbp
0x18015c65a  pop     rbx
0x18015c65b  retn
```
