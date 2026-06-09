# TProviderInfo::TProviderInfo(void *,_DRIVER_INFO_3W *,HINSTANCE__ *,ushort *,ushort *,tagSHIMOPTS,ulong,IPrintTicketProvider *)

- ea: `0x180005ea0`
- end: `0x1800060f3`
- name: `??0TProviderInfo@@QEAA@PEAXPEAU_DRIVER_INFO_3W@@PEAUHINSTANCE__@@PEAG3W4tagSHIMOPTS@@KPEAUIPrintTicketProvider@@@Z`
- size: `595`
- prototype: `TProviderInfo *__fastcall(TProviderInfo *__hidden this, void *, struct _DRIVER_INFO_3W *, HINSTANCE, unsigned __int16 *, unsigned __int16 *, enum tagSHIMOPTS, unsigned int, struct IPrintTicketProvider *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007b9c`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180005ea0`
- `0x1800060fc`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005f2c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006030`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800060a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005f2c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006030`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800060a2`
- `KERNEL32!LoadLibraryExW` at `0x1800060b5`
- `KERNEL32!LoadLibraryExW` at `0x1800060b5`
- `KERNEL32!GetProcessHeap` at `0x18000605c`
- `KERNEL32!GetProcessHeap` at `0x18000605c`
- `KERNEL32!HeapAlloc` at `0x18000606a`
- `KERNEL32!HeapAlloc` at `0x18000606a`

## string_xrefs

- `0x180005f21`: `tsprint.dll`

## pseudocode

```c
TProviderInfo *__fastcall TProviderInfo::TProviderInfo(
        TProviderInfo *this,
        void *a2,
        struct _DRIVER_INFO_3W *a3,
        HINSTANCE a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        enum tagSHIMOPTS a7,
        unsigned int a8,
        struct IPrintTicketProvider *a9)
{
  LPWSTR v11; // rdx
  __int64 v12; // rax
  LPWSTR pConfigFile; // rcx
  bool v14; // zf
  int v15; // eax
  unsigned int v16; // r14d
  LPWSTR pDependentFiles; // rsi
  __int64 v18; // rbx
  __int64 v19; // rax
  HANDLE ProcessHeap; // rax
  LPVOID v21; // rax
  const WCHAR *v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rax

  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &TProviderInfo::`vftable';
  *((_DWORD *)this + 10) = a8;
  v11 = 0;
  *((_DWORD *)this + 11) = a7;
  LODWORD(v12) = 0;
  *((_QWORD *)this + 4) = a4;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  if ( a3 )
  {
    pConfigFile = a3->pConfigFile;
    if ( pConfigFile )
    {
      v11 = a3->pConfigFile;
      v12 = -1;
      do
        ++v12;
      while ( pConfigFile[v12] );
    }
  }
  if ( (unsigned int)v12 < dword_180031E14
    || (v14 = (unsigned int)_o__wcsicmp(L"tsprint.dll", &v11[(unsigned int)(v12 - dword_180031E14)]) == 0, v15 = 1, !v14) )
  {
    v15 = 0;
  }
  *((_DWORD *)this + 15) = v15;
  *((_QWORD *)this + 8) = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset((char *)this + 80);
  *((_QWORD *)this + 10) = a6;
  *((_QWORD *)this + 11) = 0;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset((char *)this + 88);
  *((_QWORD *)this + 11) = a5;
  *((_QWORD *)this + 12) = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 2) = this;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((char *)this + 104);
  *((_QWORD *)this + 13) = a9;
  if ( a9 )
    ((void (__fastcall *)(struct IPrintTicketProvider *))a9->lpVtbl->AddRef)(a9);
  if ( *((_QWORD *)this + 3) && a3 && a3->pDependentFiles && !*((_QWORD *)this + 13) )
  {
    *((_DWORD *)this + 14) = 0;
    v16 = 0;
    pDependentFiles = a3->pDependentFiles;
    v18 = -1;
    do
      ++v18;
    while ( pDependentFiles[v18] );
    while ( (_DWORD)v18 )
    {
      if ( (unsigned int)v18 > 4 && !(unsigned int)_o__wcsicmp(&pDependentFiles[(unsigned int)v18 - 4], L".dll") )
        ++v16;
      v19 = (unsigned int)(v18 + 1);
      v18 = -1;
      pDependentFiles += v19;
      do
        ++v18;
      while ( pDependentFiles[v18] );
    }
    ProcessHeap = GetProcessHeap();
    v21 = HeapAlloc(ProcessHeap, 0, 8LL * v16);
    *((_QWORD *)this + 6) = v21;
    if ( v21 )
    {
      v22 = a3->pDependentFiles;
      v23 = -1;
      do
        ++v23;
      while ( v22[v23] );
      while ( (_DWORD)v23 )
      {
        if ( (unsigned int)v23 > 4 && !(unsigned int)_o__wcsicmp(&v22[(unsigned int)v23 - 4], L".dll") )
          *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * (unsigned int)(*((_DWORD *)this + 14))++) = LoadLibraryExW(
                                                                                                  v22,
                                                                                                  0,
                                                                                                  0xAu);
        v24 = (unsigned int)(v23 + 1);
        v23 = -1;
        v22 += v24;
        do
          ++v23;
        while ( v22[v23] );
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180005ea0  push    rbx
0x180005ea2  push    rbp
0x180005ea3  push    rsi
0x180005ea4  push    rdi
0x180005ea5  push    r12
0x180005ea7  push    r14
0x180005ea9  push    r15
0x180005eab  sub     rsp, 20h
0x180005eaf  xor     r15d, r15d
0x180005eb2  mov     [rcx+18h], rdx
0x180005eb6  lea     rax, ??_7TProviderInfo@@6B@; const TProviderInfo::`vftable'
0x180005ebd  mov     dword ptr [rcx+8], 1
0x180005ec4  mov     [rcx], rax
0x180005ec7  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005ecb  mov     eax, [rsp+58h+arg_38]
0x180005ed2  mov     rbp, r8
0x180005ed5  mov     [rcx+28h], eax
0x180005ed8  mov     rdi, rcx
0x180005edb  mov     eax, [rsp+58h+arg_30]
0x180005ee2  mov     edx, r15d
0x180005ee5  mov     [rcx+2Ch], eax
0x180005ee8  mov     eax, r15d
0x180005eeb  mov     [rcx+20h], r9
0x180005eef  mov     [rcx+30h], r15
0x180005ef3  mov     [rcx+38h], r15d
0x180005ef7  test    r8, r8
0x180005efa  jz      short loc_180005F15
0x180005efc  mov     rcx, [r8+28h]
0x180005f00  test    rcx, rcx
0x180005f03  jz      short loc_180005F15
0x180005f05  mov     rdx, rcx
0x180005f08  mov     rax, r12
0x180005f0b  inc     rax
0x180005f0e  cmp     [rcx+rax*2], r15w
0x180005f13  jnz     short loc_180005F0B
0x180005f15  mov     ecx, cs:dword_180031E14
0x180005f1b  cmp     eax, ecx
0x180005f1d  jb      short loc_180005F3B
0x180005f1f  sub     eax, ecx
0x180005f21  lea     rcx, aTsprintDll; "tsprint.dll"
0x180005f28  lea     rdx, [rdx+rax*2]
0x180005f2c  call    cs:__imp__o__wcsicmp
0x180005f32  test    eax, eax
0x180005f34  mov     eax, 1
0x180005f39  jz      short loc_180005F3E
0x180005f3b  mov     eax, r15d
0x180005f3e  lea     rbx, [rdi+40h]
0x180005f42  mov     [rdi+3Ch], eax
0x180005f45  mov     rcx, rbx
0x180005f48  mov     [rbx], r15
0x180005f4b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180005f50  mov     [rbx], r15
0x180005f53  lea     rbx, [rdi+48h]
0x180005f57  mov     rcx, rbx
0x180005f5a  mov     [rbx], r15
0x180005f5d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180005f62  mov     [rbx], r15
0x180005f65  lea     rbx, [rdi+50h]
0x180005f69  mov     rcx, rbx
0x180005f6c  mov     [rbx], r15
0x180005f6f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180005f74  mov     rax, [rsp+58h+arg_28]
0x180005f7c  mov     [rbx], rax
0x180005f7f  lea     rbx, [rdi+58h]
0x180005f83  mov     rcx, rbx
0x180005f86  mov     [rbx], r15
0x180005f89  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180005f8e  mov     rax, [rsp+58h+arg_20]
0x180005f96  mov     [rbx], rax
0x180005f99  lea     rbx, [rdi+60h]
0x180005f9d  mov     rcx, rbx
0x180005fa0  mov     [rbx], r15
0x180005fa3  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x180005fa8  mov     [rbx], r15
0x180005fab  lea     rbx, [rdi+68h]
0x180005faf  mov     [rbx], r15
0x180005fb2  mov     rcx, rbx
0x180005fb5  mov     [rdi+10h], rdi
0x180005fb9  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180005fbe  mov     rcx, [rsp+58h+arg_40]
0x180005fc6  mov     [rbx], rcx
0x180005fc9  test    rcx, rcx
0x180005fcc  jz      short loc_180005FDA
0x180005fce  mov     rax, [rcx]
0x180005fd1  mov     rax, [rax+8]
0x180005fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fda  cmp     [rdi+18h], r15
0x180005fde  jz      loc_1800060E1
0x180005fe4  test    rbp, rbp
0x180005fe7  jz      loc_1800060E1
0x180005fed  cmp     [rbp+38h], r15
0x180005ff1  jz      loc_1800060E1
0x180005ff7  cmp     [rbx], r15
0x180005ffa  jnz     loc_1800060E1
0x180006000  mov     [rdi+38h], r15d
0x180006004  mov     r14d, r15d
0x180006007  mov     rsi, [rbp+38h]
0x18000600b  mov     rbx, r12
0x18000600e  inc     rbx
0x180006011  cmp     [rsi+rbx*2], r15w
0x180006016  jnz     short loc_18000600E
0x180006018  jmp     short loc_180006051
0x18000601a  cmp     ebx, 4
0x18000601d  jbe     short loc_18000603D
0x18000601f  mov     eax, ebx
0x180006021  lea     rdx, aDll; ".dll"
0x180006028  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000602c  lea     rcx, [rsi+rax*2]
0x180006030  call    cs:__imp__o__wcsicmp
0x180006036  test    eax, eax
0x180006038  jnz     short loc_18000603D
0x18000603a  inc     r14d
0x18000603d  lea     eax, [rbx+1]
0x180006040  mov     rbx, r12
0x180006043  lea     rsi, [rsi+rax*2]
0x180006047  inc     rbx
0x18000604a  cmp     [rsi+rbx*2], r15w
0x18000604f  jnz     short loc_180006047
0x180006051  test    ebx, ebx
0x180006053  jnz     short loc_18000601A
0x180006055  mov     ebx, r14d
0x180006058  shl     rbx, 3
0x18000605c  call    cs:__imp_GetProcessHeap
0x180006062  mov     r8, rbx; dwBytes
0x180006065  xor     edx, edx; dwFlags
0x180006067  mov     rcx, rax; hHeap
0x18000606a  call    cs:__imp_HeapAlloc
0x180006070  mov     [rdi+30h], rax
0x180006074  test    rax, rax
0x180006077  jz      short loc_1800060E1
0x180006079  mov     rsi, [rbp+38h]
0x18000607d  mov     rbx, r12
0x180006080  inc     rbx
0x180006083  cmp     [rsi+rbx*2], r15w
0x180006088  jnz     short loc_180006080
0x18000608a  jmp     short loc_1800060DD
0x18000608c  cmp     ebx, 4
0x18000608f  jbe     short loc_1800060C9
0x180006091  mov     eax, ebx
0x180006093  lea     rdx, aDll; ".dll"
0x18000609a  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000609e  lea     rcx, [rsi+rax*2]
0x1800060a2  call    cs:__imp__o__wcsicmp
0x1800060a8  test    eax, eax
0x1800060aa  jnz     short loc_1800060C9
0x1800060ac  xor     edx, edx; hFile
0x1800060ae  lea     r8d, [rax+0Ah]; dwFlags
0x1800060b2  mov     rcx, rsi; lpLibFileName
0x1800060b5  call    cs:__imp_LoadLibraryExW
0x1800060bb  mov     edx, [rdi+38h]
0x1800060be  mov     rcx, [rdi+30h]
0x1800060c2  mov     [rcx+rdx*8], rax
0x1800060c6  inc     dword ptr [rdi+38h]
0x1800060c9  lea     eax, [rbx+1]
0x1800060cc  mov     rbx, r12
0x1800060cf  lea     rsi, [rsi+rax*2]
0x1800060d3  inc     rbx
0x1800060d6  cmp     [rsi+rbx*2], r15w
0x1800060db  jnz     short loc_1800060D3
0x1800060dd  test    ebx, ebx
0x1800060df  jnz     short loc_18000608C
0x1800060e1  mov     rax, rdi
0x1800060e4  add     rsp, 20h
0x1800060e8  pop     r15
0x1800060ea  pop     r14
0x1800060ec  pop     r12
0x1800060ee  pop     rdi
0x1800060ef  pop     rsi
0x1800060f0  pop     rbp
0x1800060f1  pop     rbx
0x1800060f2  retn
```
