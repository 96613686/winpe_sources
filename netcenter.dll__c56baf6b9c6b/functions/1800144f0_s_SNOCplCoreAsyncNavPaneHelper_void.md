# s_SNOCplCoreAsyncNavPaneHelper(void *)

- ea: `0x1800144f0`
- end: `0x1800146be`
- name: `?s_SNOCplCoreAsyncNavPaneHelper@@YAKPEAX@Z`
- size: `462`
- prototype: `unsigned int __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002294`
- `0x18000400c`
- `0x1800080a8`
- `0x180008d70`
- `0x180010e9c`
- `0x1800135a0`
- `0x1800144f0`
- `0x18001a7a0`
- `0x18001aac8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014612`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800146a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800146a4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014510`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014510`
- `SHLWAPI!SHStrDupW` at `0x1800145b4`
- `SHLWAPI!SHStrDupW` at `0x1800145c6`
- `SHLWAPI!SHStrDupW` at `0x1800145b4`
- `SHLWAPI!SHStrDupW` at `0x1800145c6`
- `USER32!PostMessageW` at `0x1800145e5`
- `USER32!PostMessageW` at `0x18001469e`
- `USER32!PostMessageW` at `0x1800145e5`
- `USER32!PostMessageW` at `0x18001469e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_SNOCplCoreAsyncNavPaneHelper(LPARAM hWnd)
{
  HWND v1; // r15
  unsigned __int64 v2; // rdx
  HRESULT SeeAlsoApplets; // esi
  LPCWSTR ***v4; // rax
  LPCWSTR ***v5; // rdi
  WCHAR *j; // rcx
  LPCWSTR *v7; // rbx
  LPARAM v8; // r14
  WCHAR *i; // rax
  LPARAM lParam; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR ***v12; // [rsp+58h] [rbp+10h]

  lParam = hWnd;
  v1 = (HWND)hWnd;
  SeeAlsoApplets = CoInitializeEx(0, 2u);
  if ( SeeAlsoApplets >= 0 )
  {
    v4 = (LPCWSTR ***)DirectUI::HAllocAndZero((DirectUI *)0x10, v2);
    v5 = v4;
    v12 = v4;
    if ( v4 )
    {
      try
      {
        *v4 = 0;
        v4[1] = 0;
        std::_Tree<std::_Tmap_traits<unsigned short *,unsigned short *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,unsigned short *>>,0>>::_Alloc_sentinel_and_proxy(v4);
      }
      catch ( ... )
      {
        v1 = (HWND)lParam;
        goto LABEL_26;
      }
    }
    else
    {
      v5 = 0;
    }
    if ( v5 )
    {
      SeeAlsoApplets = LoadSeeAlsoApplets(v5);
      if ( SeeAlsoApplets >= 0 && v5[1] )
      {
        v7 = **v5;
        while ( v7 != (LPCWSTR *)*v5 )
        {
          lParam = 0;
          if ( CTCoAllocPolicy::Alloc(j, 1u, 0x18u, (void **)&lParam) >= 0 )
          {
            v8 = lParam;
            if ( SHStrDupW(v7[4], (LPWSTR *)(lParam + 8)) >= 0 && SHStrDupW(v7[5], (LPWSTR *)(v8 + 16)) >= 0 )
            {
              *(_DWORD *)v8 = 1;
              if ( PostMessageW(v1, 0x8011u, 0, v8) )
                goto LABEL_16;
              SeeAlsoApplets = ResultFromKnownLastError();
            }
            if ( v8 )
            {
              CoTaskMemFree(*(LPVOID *)(v8 + 8));
              CoTaskMemFree(*(LPVOID *)(v8 + 16));
              CoTaskMemFree((LPVOID)v8);
            }
          }
LABEL_16:
          j = (WCHAR *)v7[2];
          if ( *((_BYTE *)j + 25) )
          {
            for ( i = (WCHAR *)v7[1]; !*((_BYTE *)i + 25) && v7 == *((LPCWSTR **)i + 2); i = (WCHAR *)*((_QWORD *)i + 1) )
              v7 = (LPCWSTR *)i;
            v7 = (LPCWSTR *)i;
          }
          else
          {
            v7 = (LPCWSTR *)v7[2];
            for ( j = *(WCHAR **)j; !*((_BYTE *)j + 25); j = *(WCHAR **)j )
              v7 = (LPCWSTR *)j;
          }
        }
      }
      CleanupSeeAlsoMap(v5);
      std::_Tree<std::_Tmap_traits<unsigned short *,unsigned short *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,unsigned short *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,unsigned short *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,unsigned short *>>,0>>(v5);
      operator delete(v5, 0x10u);
    }
    else
    {
LABEL_26:
      SeeAlsoApplets = -2147024882;
    }
    PostMessageW(v1, 0x8012u, 0, 0);
    CoUninitialize();
  }
  return (unsigned int)SeeAlsoApplets;
}

```

## disassembly

```asm
0x1800144f0  mov     [rsp+arg_10], rbx
0x1800144f5  mov     [rsp+lParam], rcx
0x1800144fa  push    rsi
0x1800144fb  push    rdi
0x1800144fc  push    r12
0x1800144fe  push    r14
0x180014500  push    r15
0x180014502  sub     rsp, 20h
0x180014506  mov     r15, rcx
0x180014509  mov     edx, 2; dwCoInit
0x18001450e  xor     ecx, ecx; pvReserved
0x180014510  call    cs:__imp_CoInitializeEx
0x180014516  mov     esi, eax
0x180014518  test    eax, eax
0x18001451a  js      loc_1800146AA
0x180014520  mov     ecx, 10h; this
0x180014525  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001452a  mov     rdi, rax
0x18001452d  mov     [rsp+48h+arg_8], rax
0x180014532  test    rax, rax
0x180014535  jz      short loc_180014550
0x180014537  mov     qword ptr [rax], 0
0x18001453e  mov     qword ptr [rax+8], 0
0x180014546  mov     rcx, rax
0x180014549  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001454e  jmp     short loc_180014552
0x180014550  xor     edi, edi
0x180014552  test    rdi, rdi
0x180014555  jz      loc_18001468B
0x18001455b  mov     rcx, rdi
0x18001455e  call    ?LoadSeeAlsoApplets@@YAJPEAV?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@@Z; LoadSeeAlsoApplets(std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>> *)
0x180014563  mov     esi, eax
0x180014565  test    eax, eax
0x180014567  js      loc_180014667
0x18001456d  cmp     qword ptr [rdi+8], 0
0x180014572  jz      loc_180014667
0x180014578  mov     rbx, [rdi]
0x18001457b  mov     rbx, [rbx]
0x18001457e  cmp     rbx, [rdi]
0x180014581  jz      loc_180014667
0x180014587  mov     [rsp+48h+lParam], 0
0x180014590  lea     r9, [rsp+48h+lParam]; void **
0x180014595  mov     edx, 1; unsigned int
0x18001459a  lea     r8d, [rdx+17h]; unsigned __int64
0x18001459e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800145a3  test    eax, eax
0x1800145a5  js      short loc_180014618
0x1800145a7  mov     r14, [rsp+48h+lParam]
0x1800145ac  lea     rdx, [r14+8]; ppwsz
0x1800145b0  mov     rcx, [rbx+20h]; psz
0x1800145b4  call    cs:__imp_SHStrDupW
0x1800145ba  test    eax, eax
0x1800145bc  js      short loc_1800145F6
0x1800145be  lea     rdx, [r14+10h]; ppwsz
0x1800145c2  mov     rcx, [rbx+28h]; psz
0x1800145c6  call    cs:__imp_SHStrDupW
0x1800145cc  test    eax, eax
0x1800145ce  js      short loc_1800145F6
0x1800145d0  mov     dword ptr [r14], 1
0x1800145d7  mov     r9, r14; lParam
0x1800145da  xor     r8d, r8d; wParam
0x1800145dd  mov     edx, 8011h; Msg
0x1800145e2  mov     rcx, r15; hWnd
0x1800145e5  call    cs:__imp_PostMessageW
0x1800145eb  test    eax, eax
0x1800145ed  jnz     short loc_180014618
0x1800145ef  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800145f4  mov     esi, eax
0x1800145f6  test    r14, r14
0x1800145f9  jz      short loc_180014618
0x1800145fb  mov     rcx, [r14+8]; pv
0x1800145ff  call    cs:__imp_CoTaskMemFree
0x180014605  mov     rcx, [r14+10h]; pv
0x180014609  call    cs:__imp_CoTaskMemFree
0x18001460f  mov     rcx, r14; pv
0x180014612  call    cs:__imp_CoTaskMemFree
0x180014618  mov     rcx, [rbx+10h]
0x18001461c  cmp     byte ptr [rcx+19h], 0
0x180014620  jz      short loc_180014643
0x180014622  mov     rax, [rbx+8]
0x180014626  jmp     short loc_180014635
0x180014628  cmp     rbx, [rax+10h]
0x18001462c  jnz     short loc_18001463B
0x18001462e  mov     rbx, rax
0x180014631  mov     rax, [rax+8]
0x180014635  cmp     byte ptr [rax+19h], 0
0x180014639  jz      short loc_180014628
0x18001463b  mov     rbx, rax
0x18001463e  jmp     loc_18001457E
0x180014643  mov     rbx, rcx
0x180014646  mov     rcx, [rcx]
0x180014649  cmp     byte ptr [rcx+19h], 0
0x18001464d  jnz     loc_18001457E
0x180014653  mov     rbx, rcx
0x180014656  mov     rax, [rcx]
0x180014659  mov     rcx, rax
0x18001465c  cmp     byte ptr [rax+19h], 0
0x180014660  jz      short loc_180014653
0x180014662  jmp     loc_18001457E
0x180014667  mov     rcx, rdi
0x18001466a  call    ?CleanupSeeAlsoMap@@YAXPEAV?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@@Z; CleanupSeeAlsoMap(std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>> *)
0x18001466f  mov     rcx, rdi
0x180014672  call    ??1?$_Tree@V?$_Tmap_traits@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>,0>>::~_Tree<std::_Tmap_traits<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>,0>>(void)
0x180014677  mov     edx, 10h; unsigned __int64
0x18001467c  mov     rcx, rdi; void *
0x18001467f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014684  jmp     short loc_180014690
0x180014686  mov     r15, [rsp+48h+lParam]
0x18001468b  mov     esi, 8007000Eh
0x180014690  xor     r9d, r9d; lParam
0x180014693  xor     r8d, r8d; wParam
0x180014696  mov     edx, 8012h; Msg
0x18001469b  mov     rcx, r15; hWnd
0x18001469e  call    cs:__imp_PostMessageW
0x1800146a4  call    cs:__imp_CoUninitialize
0x1800146aa  mov     eax, esi
0x1800146ac  mov     rbx, [rsp+48h+arg_10]
0x1800146b1  add     rsp, 20h
0x1800146b5  pop     r15
0x1800146b7  pop     r14
0x1800146b9  pop     r12
0x1800146bb  pop     rdi
0x1800146bc  pop     rsi
0x1800146bd  retn
```
