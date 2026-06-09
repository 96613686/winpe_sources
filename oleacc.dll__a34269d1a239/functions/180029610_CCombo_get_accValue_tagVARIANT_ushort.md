# CCombo::get_accValue(tagVARIANT,ushort * *)

- ea: `0x180029610`
- end: `0x18002992b`
- name: `?get_accValue@CCombo@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `795`
- prototype: `__int64 __fastcall(CCombo *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002dd4`
- `0x180004720`
- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18002875c`
- `0x180029610`
- `0x18002dae8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180029798`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180029798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002975b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002975b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298b0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800297a1`
- `OLEAUT32!__imp_SysAllocString` at `0x180029904`
- `OLEAUT32!__imp_SysAllocString` at `0x1800297a1`
- `OLEAUT32!__imp_SysAllocString` at `0x180029904`
- `USER32!GetWindowLongW` at `0x1800297fe`
- `USER32!GetWindowLongW` at `0x1800297fe`

## pseudocode

```c
int __fastcall CCombo::get_accValue(CCombo *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  int result; // eax
  unsigned int Lo; // ecx
  int v8; // eax
  HWND v9; // rcx
  unsigned __int64 v10; // rdi
  SIZE_T v11; // rcx
  void *v12; // rsi
  int v13; // ebx
  SIZE_T v14; // rdi
  _WORD *v15; // rbx
  HANDLE v16; // rcx
  unsigned __int16 *v17; // rax
  HANDLE v18; // rdx
  void *v19; // rcx
  HWND v20; // rdi
  CCombo *v21; // rcx
  char WindowLongW; // al
  unsigned __int64 v23; // r15
  unsigned int v24; // ecx
  unsigned __int64 v25; // rax
  _WORD *v26; // rax
  void *v27; // rsi
  unsigned __int64 v28; // [rsp+70h] [rbp+30h] BYREF
  HANDLE hProcess; // [rsp+80h] [rbp+40h] BYREF

  *a3 = 0;
  if ( !(*(unsigned int (__fastcall **)(CCombo *))(*(_QWORD *)this + 240LL))(this) )
    return -2147024809;
  Lo = a2->cyVal.Lo;
  v28 = 0;
  if ( Lo >= 2 )
    return -2147352573;
  v8 = IsTridentControl(*((_DWORD *)this + 25), *((_DWORD *)this + 17), *((HWND *)this + 10), 1, 0);
  v9 = (HWND)*((_QWORD *)this + 10);
  if ( v8 )
  {
    hProcess = 0;
    result = CAccessible::AccSendMessageTimeout(this, 0, v9, 0x200Eu, 0, 0, (__int64 *)&v28);
    if ( result < 0 )
      return result;
    v10 = (unsigned int)v28;
    if ( (int)v28 + 1 >= (unsigned int)v28 )
    {
      v11 = 2LL * (unsigned int)(v28 + 1);
      if ( v11 <= 0xFFFFFFFF )
      {
        v12 = SharedAlloc(v11, *((HWND *)this + 10), &hProcess);
        if ( v12 )
        {
          v13 = CAccessible::AccSendMessageTimeout(
                  this,
                  0,
                  *((HWND *)this + 10),
                  0x200Du,
                  v10,
                  (__int64)v12,
                  (__int64 *)&v28);
          if ( v13 < 0 )
          {
LABEL_15:
            SharedFree(v12, hProcess);
            return v13;
          }
          if ( (unsigned int)v28 > (unsigned int)v10 )
          {
            v13 = 1;
            goto LABEL_15;
          }
          v14 = (unsigned int)(2 * v28 + 2);
          v15 = LocalAlloc(0x40u, v14);
          if ( !v15 )
          {
            v13 = -2147024882;
            goto LABEL_15;
          }
          v16 = hProcess;
          *v15 = 0;
          ReadProcessMemory(v16, v12, v15, v14, 0);
          v17 = SysAllocString(v15);
          v18 = hProcess;
          *a3 = v17;
          SharedFree(v12, v18);
          v19 = v15;
          goto LABEL_18;
        }
        return -2147024882;
      }
    }
    return -2147024362;
  }
  v20 = IsInComboEx(v9);
  if ( !v20 )
    v20 = (HWND)*((_QWORD *)this + 10);
  if ( !IsComboEx(v20) )
  {
    v21 = this;
    return CCombo::HrGetWindowNameNoLabelNoMnemonic(v21, v20, a3);
  }
  WindowLongW = GetWindowLongW(v20, -16);
  v21 = this;
  if ( (WindowLongW & 3) == 0 )
    return CCombo::HrGetWindowNameNoLabelNoMnemonic(v21, v20, a3);
  result = CAccessible::AccSendMessageTimeout(this, 0, v20, 0x147u, 0, 0, (__int64 *)&v28);
  if ( result < 0 )
    return result;
  if ( (_DWORD)v28 == -1 )
    return 1;
  v23 = (int)v28;
  result = CAccessible::AccSendMessageTimeout(this, 0, v20, 0x149u, (int)v28, 0, (__int64 *)&v28);
  if ( result >= 0 )
  {
    if ( (unsigned int)v28 >= 0x400 )
    {
      v24 = v28 + 1;
      if ( (int)v28 + 1 < (unsigned int)v28 )
        return -2147024362;
    }
    else
    {
      v24 = 1025;
    }
    v25 = 2LL * v24;
    if ( v25 <= 0xFFFFFFFF )
    {
      v26 = LocalAlloc(0x40u, (unsigned int)v25);
      v27 = v26;
      if ( v26 )
      {
        *v26 = 0;
        v13 = CAccessible::AccSendMessageTimeout(this, 0, v20, 0x148u, v23, (__int64)v26, (__int64 *)&v28);
        if ( v13 < 0 )
        {
          LocalFree(v27);
          return v13;
        }
        *a3 = SysAllocString((const OLECHAR *)v27);
        v19 = v27;
LABEL_18:
        LocalFree(v19);
        return 0;
      }
      return -2147024882;
    }
    return -2147024362;
  }
  return result;
}

```

## disassembly

```asm
0x180029610  mov     [rsp-28h+arg_8], rbx
0x180029615  push    rbp
0x180029616  push    rsi
0x180029617  push    rdi
0x180029618  push    r14
0x18002961a  push    r15
0x18002961c  mov     rbp, rsp
0x18002961f  sub     rsp, 40h
0x180029623  mov     qword ptr [r8], 0
0x18002962a  mov     r14, r8
0x18002962d  mov     rax, [rcx]
0x180029630  mov     rdi, rdx
0x180029633  mov     rbx, rcx
0x180029636  mov     rax, [rax+0F0h]
0x18002963d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029642  test    eax, eax
0x180029644  jnz     short loc_180029650
0x180029646  mov     eax, 80070057h
0x18002964b  jmp     loc_18002991A
0x180029650  mov     ecx, [rdi+8]
0x180029653  mov     [rbp+arg_0], 0
0x18002965b  test    ecx, ecx
0x18002965d  jz      short loc_18002966E
0x18002965f  cmp     ecx, 1
0x180029662  jz      short loc_18002966E
0x180029664  mov     eax, 80020003h
0x180029669  jmp     loc_18002991A
0x18002966e  mov     r8, [rbx+50h]; HWND
0x180029672  mov     r15d, 1
0x180029678  mov     edx, [rbx+44h]; unsigned int
0x18002967b  mov     r9d, r15d; int
0x18002967e  mov     ecx, [rbx+64h]; unsigned int
0x180029681  mov     dword ptr [rsp+40h+lpNumberOfBytesRead], 0; int
0x180029689  call    ?IsTridentControl@@YAHKKPEAUHWND__@@HH@Z; IsTridentControl(ulong,ulong,HWND__ *,int,int)
0x18002968e  mov     rcx, [rbx+50h]; hWnd
0x180029692  test    eax, eax
0x180029694  jz      loc_1800297C6
0x18002969a  lea     rax, [rbp+arg_0]
0x18002969e  mov     [rbp+hProcess], 0
0x1800296a6  mov     [rsp+40h+var_10], rax; __int64 *
0x1800296ab  mov     r8, rcx; HWND
0x1800296ae  mov     [rsp+40h+var_18], 0; __int64
0x1800296b7  mov     r9d, 200Eh; unsigned int
0x1800296bd  xor     edx, edx; bool
0x1800296bf  mov     [rsp+40h+lpNumberOfBytesRead], 0; unsigned __int64
0x1800296c8  mov     rcx, rbx; this
0x1800296cb  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800296d0  test    eax, eax
0x1800296d2  js      loc_18002991A
0x1800296d8  mov     edi, dword ptr [rbp+arg_0]
0x1800296db  lea     eax, [rdi+1]
0x1800296de  cmp     eax, edi
0x1800296e0  jb      loc_180029915
0x1800296e6  mov     ecx, eax
0x1800296e8  mov     edx, 0FFFFFFFFh
0x1800296ed  add     rcx, rcx; dwSize
0x1800296f0  cmp     rcx, rdx
0x1800296f3  ja      loc_180029915
0x1800296f9  mov     rdx, [rbx+50h]; HWND
0x1800296fd  lea     r8, [rbp+hProcess]; void **
0x180029701  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180029706  mov     rsi, rax
0x180029709  test    rax, rax
0x18002970c  jz      loc_1800298BE
0x180029712  mov     r8, [rbx+50h]; HWND
0x180029716  lea     rax, [rbp+arg_0]
0x18002971a  mov     [rsp+40h+var_10], rax; __int64 *
0x18002971f  mov     r9d, 200Dh; unsigned int
0x180029725  mov     [rsp+40h+var_18], rsi; __int64
0x18002972a  xor     edx, edx; bool
0x18002972c  mov     rcx, rbx; this
0x18002972f  mov     [rsp+40h+lpNumberOfBytesRead], rdi; unsigned __int64
0x180029734  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180029739  mov     ebx, eax
0x18002973b  test    eax, eax
0x18002973d  js      short loc_18002976E
0x18002973f  mov     eax, dword ptr [rbp+arg_0]
0x180029742  cmp     eax, edi
0x180029744  jbe     short loc_18002974B
0x180029746  mov     ebx, r15d
0x180029749  jmp     short loc_18002976E
0x18002974b  lea     eax, ds:2[rax*2]
0x180029752  mov     ecx, 40h ; '@'; uFlags
0x180029757  mov     edx, eax; uBytes
0x180029759  mov     edi, eax
0x18002975b  call    cs:__imp_LocalAlloc
0x180029761  mov     rbx, rax
0x180029764  test    rax, rax
0x180029767  jnz     short loc_180029781
0x180029769  mov     ebx, 8007000Eh
0x18002976e  mov     rdx, [rbp+hProcess]; hProcess
0x180029772  mov     rcx, rsi; lpAddress
0x180029775  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002977a  mov     eax, ebx
0x18002977c  jmp     loc_18002991A
0x180029781  mov     rcx, [rbp+hProcess]; hProcess
0x180029785  xor     eax, eax
0x180029787  mov     r9, rdi; nSize
0x18002978a  mov     [rbx], ax
0x18002978d  mov     r8, rbx; lpBuffer
0x180029790  mov     [rsp+40h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180029795  mov     rdx, rsi; lpBaseAddress
0x180029798  call    cs:__imp_ReadProcessMemory
0x18002979e  mov     rcx, rbx; psz
0x1800297a1  call    cs:__imp_SysAllocString
0x1800297a7  mov     rdx, [rbp+hProcess]; hProcess
0x1800297ab  mov     rcx, rsi; lpAddress
0x1800297ae  mov     [r14], rax
0x1800297b1  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800297b6  mov     rcx, rbx; hMem
0x1800297b9  call    cs:__imp_LocalFree
0x1800297bf  xor     eax, eax
0x1800297c1  jmp     loc_18002991A
0x1800297c6  call    ?IsInComboEx@@YAPEAUHWND__@@PEAU1@@Z; IsInComboEx(HWND__ *)
0x1800297cb  mov     rdi, rax
0x1800297ce  test    rax, rax
0x1800297d1  jnz     short loc_1800297D7
0x1800297d3  mov     rdi, [rbx+50h]
0x1800297d7  mov     rcx, rdi; HWND
0x1800297da  call    ?IsComboEx@@YAHPEAUHWND__@@@Z; IsComboEx(HWND__ *)
0x1800297df  test    eax, eax
0x1800297e1  jnz     short loc_1800297F6
0x1800297e3  mov     rcx, rbx; this
0x1800297e6  mov     rdx, rdi; HWND
0x1800297e9  mov     r8, r14; unsigned __int16 **
0x1800297ec  call    ?HrGetWindowNameNoLabelNoMnemonic@CCombo@@AEAAJPEAUHWND__@@PEAPEAG@Z; CCombo::HrGetWindowNameNoLabelNoMnemonic(HWND__ *,ushort * *)
0x1800297f1  jmp     loc_18002991A
0x1800297f6  mov     edx, 0FFFFFFF0h; nIndex
0x1800297fb  mov     rcx, rdi; hWnd
0x1800297fe  call    cs:__imp_GetWindowLongW
0x180029804  mov     rcx, rbx; this
0x180029807  test    al, 3
0x180029809  jz      short loc_1800297E6
0x18002980b  lea     rax, [rbp+arg_0]
0x18002980f  mov     r9d, 147h; unsigned int
0x180029815  mov     [rsp+40h+var_10], rax; __int64 *
0x18002981a  mov     r8, rdi; HWND
0x18002981d  mov     [rsp+40h+var_18], 0; __int64
0x180029826  xor     edx, edx; bool
0x180029828  mov     [rsp+40h+lpNumberOfBytesRead], 0; unsigned __int64
0x180029831  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180029836  test    eax, eax
0x180029838  js      loc_18002991A
0x18002983e  cmp     dword ptr [rbp+arg_0], 0FFFFFFFFh
0x180029842  jnz     short loc_18002984C
0x180029844  mov     eax, r15d
0x180029847  jmp     loc_18002991A
0x18002984c  movsxd  r15, dword ptr [rbp+arg_0]
0x180029850  lea     rax, [rbp+arg_0]
0x180029854  mov     [rsp+40h+var_10], rax; __int64 *
0x180029859  mov     r9d, 149h; unsigned int
0x18002985f  mov     [rsp+40h+var_18], 0; __int64
0x180029868  mov     r8, rdi; HWND
0x18002986b  xor     edx, edx; bool
0x18002986d  mov     [rsp+40h+lpNumberOfBytesRead], r15; unsigned __int64
0x180029872  mov     rcx, rbx; this
0x180029875  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002987a  test    eax, eax
0x18002987c  js      loc_18002991A
0x180029882  mov     eax, dword ptr [rbp+arg_0]
0x180029885  cmp     eax, 400h
0x18002988a  jnb     short loc_180029893
0x18002988c  mov     ecx, 401h
0x180029891  jmp     short loc_18002989A
0x180029893  lea     ecx, [rax+1]
0x180029896  cmp     ecx, eax
0x180029898  jb      short loc_180029915
0x18002989a  mov     eax, ecx
0x18002989c  mov     edx, 0FFFFFFFFh
0x1800298a1  add     rax, rax
0x1800298a4  cmp     rax, rdx
0x1800298a7  ja      short loc_180029915
0x1800298a9  mov     edx, eax; uBytes
0x1800298ab  mov     ecx, 40h ; '@'; uFlags
0x1800298b0  call    cs:__imp_LocalAlloc
0x1800298b6  mov     rsi, rax
0x1800298b9  test    rax, rax
0x1800298bc  jnz     short loc_1800298C5
0x1800298be  mov     eax, 8007000Eh
0x1800298c3  jmp     short loc_18002991A
0x1800298c5  xor     eax, eax
0x1800298c7  mov     r9d, 148h; unsigned int
0x1800298cd  mov     [rsi], ax
0x1800298d0  mov     r8, rdi; HWND
0x1800298d3  lea     rax, [rbp+arg_0]
0x1800298d7  xor     edx, edx; bool
0x1800298d9  mov     [rsp+40h+var_10], rax; __int64 *
0x1800298de  mov     rcx, rbx; this
0x1800298e1  mov     [rsp+40h+var_18], rsi; __int64
0x1800298e6  mov     [rsp+40h+lpNumberOfBytesRead], r15; unsigned __int64
0x1800298eb  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800298f0  mov     ebx, eax
0x1800298f2  mov     rcx, rsi; psz
0x1800298f5  test    eax, eax
0x1800298f7  jns     short loc_180029904
0x1800298f9  call    cs:__imp_LocalFree
0x1800298ff  jmp     loc_18002977A
0x180029904  call    cs:__imp_SysAllocString
0x18002990a  mov     [r14], rax
0x18002990d  mov     rcx, rsi
0x180029910  jmp     loc_1800297B9
0x180029915  mov     eax, 80070216h
0x18002991a  mov     rbx, [rsp+40h+arg_8]
0x18002991f  add     rsp, 40h
0x180029923  pop     r15
0x180029925  pop     r14
0x180029927  pop     rdi
0x180029928  pop     rsi
0x180029929  pop     rbp
0x18002992a  retn
```
