# CListBox::get_accName(tagVARIANT,ushort * *)

- ea: `0x18002e6d0`
- end: `0x18002eafe`
- name: `?get_accName@CListBox@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CListBox *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002dd4`
- `0x180003240`
- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x180008870`
- `0x18000ccd0`
- `0x18001e4c0`
- `0x18001efc4`
- `0x18002dae8`
- `0x18002e6d0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e9f8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e9f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ea26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ea26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e95f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e95f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea6f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ea0a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eadf`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ea0a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eadf`
- `USER32!GetWindowLongW` at `0x18002ea5e`
- `USER32!GetWindowLongW` at `0x18002ea5e`

## pseudocode

```c
int __fastcall CListBox::get_accName(CListBox *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  int result; // eax
  int v7; // edi
  unsigned int v8; // edx
  unsigned int v9; // ecx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 (__fastcall *v11)(HANDLE, struct tagVARIANT *, unsigned __int16 **); // rax
  int v12; // ebx
  IRecordInfo *v13; // xmm1_8
  HWND hwndCombo; // r13
  HWND v15; // rax
  unsigned int v16; // r9d
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int v19; // esi
  unsigned __int64 v20; // r12
  unsigned int v21; // r14d
  void *v22; // rdi
  OLECHAR *v23; // r12
  int v24; // eax
  OLECHAR *v25; // rcx
  BSTR v26; // rax
  HANDLE v27; // rdx
  OLECHAR *v28; // rcx
  const OLECHAR *v29; // rdi
  BSTR v30; // rax
  HANDLE hProcess; // [rsp+40h] [rbp-69h] BYREF
  __int64 v32; // [rsp+48h] [rbp-61h] BYREF
  unsigned __int16 **v33; // [rsp+50h] [rbp-59h]
  SIZE_T nSize; // [rsp+58h] [rbp-51h]
  struct tagVARIANT v35; // [rsp+60h] [rbp-49h] BYREF
  struct tagCOMBOBOXINFO v36; // [rsp+80h] [rbp-29h] BYREF

  v33 = a3;
  *a3 = 0;
  if ( !(*(unsigned int (__fastcall **)(CListBox *))(*(_QWORD *)this + 240LL))(this) )
    return -2147024809;
  v7 = *((_DWORD *)this + 32);
  if ( a2->lVal )
  {
    memset_0(&v36, 0, sizeof(v36));
    if ( v7 && MyGetComboBoxInfo(*((_DWORD *)this + 25), *((_DWORD *)this + 17), *((HWND *)this + 10), &v36) )
    {
      hwndCombo = v36.hwndCombo;
      v15 = IsInComboEx(v36.hwndCombo);
      v16 = 329;
      if ( v15 )
        hwndCombo = v15;
      LODWORD(v32) = v15 != 0;
      v17 = 328;
    }
    else
    {
      hwndCombo = (HWND)*((_QWORD *)this + 10);
      v16 = 394;
      LODWORD(v32) = 0;
      v17 = 393;
    }
    v18 = a2->lVal - 1;
    hProcess = 0;
    result = CAccessible::AccSendMessageTimeout(this, 0, hwndCombo, v16, v18, 0, (__int64 *)&hProcess);
    if ( result < 0 )
      return result;
    v19 = 1024;
    if ( (unsigned int)hProcess < 0x400 )
      goto LABEL_51;
    v19 = (unsigned int)hProcess;
    if ( (_DWORD)hProcess == -1 )
      return 0;
    if ( (int)hProcess >= 0 )
    {
LABEL_51:
      if ( v19 + 1 >= v19 )
      {
        v20 = 2LL * (v19 + 1);
        if ( v20 <= 0xFFFFFFFF )
        {
          if ( (unsigned int)IsTridentControl(
                               *((_DWORD *)this + 25),
                               *((_DWORD *)this + 17),
                               *((HWND *)this + 10),
                               *((_DWORD *)this + 32),
                               *((_DWORD *)this + 32)) )
          {
            hProcess = 0;
            if ( v17 == 393 )
              v21 = 1417;
            else
              v21 = 1352;
            v22 = SharedAlloc((unsigned int)v20, hwndCombo, &hProcess);
            if ( !v22 )
              return -2147024882;
            nSize = (unsigned int)v20;
            v23 = (OLECHAR *)LocalAlloc(0x40u, (unsigned int)v20);
            if ( !v23 )
            {
              SharedFree(v22, hProcess);
              return -2147024882;
            }
            v24 = a2->lVal - 1;
            v32 = 0;
            v12 = CAccessible::AccSendMessageTimeout(this, 0, hwndCombo, v21, v24, (__int64)v22, &v32);
            if ( v12 < 0 )
              goto LABEL_35;
            if ( (unsigned int)v32 > v19 )
            {
              v12 = -2147467259;
LABEL_35:
              SharedFree(v22, hProcess);
              v25 = v23;
LABEL_36:
              LocalFree(v25);
              return v12;
            }
            ReadProcessMemory(hProcess, v22, v23, nSize, 0);
            v23[v19] = 0;
            v26 = SysAllocString(v23);
            v27 = hProcess;
            *v33 = v26;
            SharedFree(v22, v27);
            v28 = v23;
          }
          else
          {
            LODWORD(hProcess) = GetWindowLongW(*((HWND *)this + 10), -16);
            v29 = (const OLECHAR *)LocalAlloc(0x40u, (unsigned int)v20);
            if ( !v29 )
              return -2147024882;
            if ( (_DWORD)v32 || ((unsigned __int8)hProcess & 0x30) == 0 || ((unsigned __int8)hProcess & 0x40) != 0 )
            {
              v12 = CAccessible::AccSendMessageTimeout(this, 0, hwndCombo, v17, a2->lVal - 1, (__int64)v29, 0);
              if ( v12 < 0 )
              {
                v25 = (OLECHAR *)v29;
                goto LABEL_36;
              }
            }
            else
            {
              *v29 = 0;
            }
            v29[v19] = 0;
            v30 = SysAllocString(v29);
            *v33 = v30;
            v28 = (OLECHAR *)v29;
          }
          LocalFree(v28);
          return 0;
        }
      }
    }
    return -2147024362;
  }
  if ( v7 )
  {
    hProcess = 0;
    memset_0(&v36, 0, sizeof(v36));
    if ( MyGetComboBoxInfo(*((_DWORD *)this + 25), *((_DWORD *)this + 17), *((HWND *)this + 10), &v36) )
    {
      v8 = *((_DWORD *)this + 17);
      v9 = *((_DWORD *)this + 25);
      hProcess = 0;
      if ( (int)AccessibleObjectFromWindowTimeout(v9, v8, v36.hwndCombo, -4, &IID_IAccessible, &hProcess) >= 0 )
      {
        if ( hProcess )
        {
          pRecInfo = a2->pRecInfo;
          v11 = *(__int64 (__fastcall **)(HANDLE, struct tagVARIANT *, unsigned __int16 **))(*(_QWORD *)hProcess + 80LL);
          *(_OWORD *)&v35.vt = *(_OWORD *)&a2->vt;
          v35.pRecInfo = pRecInfo;
          v12 = v11(hProcess, &v35, a3);
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hProcess + 16LL))(hProcess);
          return v12;
        }
      }
    }
    return 1;
  }
  else
  {
    v13 = a2->pRecInfo;
    *(_OWORD *)&v35.vt = *(_OWORD *)&a2->vt;
    v35.pRecInfo = v13;
    return CClient::get_accName(this, &v35, a3);
  }
}

```

## disassembly

```asm
0x18002e6d0  mov     [rsp-8+arg_18], rbx
0x18002e6d5  push    rbp
0x18002e6d6  push    rsi
0x18002e6d7  push    rdi
0x18002e6d8  push    r12
0x18002e6da  push    r13
0x18002e6dc  push    r14
0x18002e6de  push    r15
0x18002e6e0  lea     rbp, [rsp-27h]
0x18002e6e5  sub     rsp, 0D0h
0x18002e6ec  mov     rax, cs:__security_cookie
0x18002e6f3  xor     rax, rsp
0x18002e6f6  mov     [rbp+57h+var_40], rax
0x18002e6fa  xor     r12d, r12d
0x18002e6fd  mov     [rbp+57h+var_B0], r8
0x18002e701  mov     [r8], r12
0x18002e704  mov     rsi, r8
0x18002e707  mov     rax, [rcx]
0x18002e70a  mov     r15, rdx
0x18002e70d  mov     rbx, rcx
0x18002e710  mov     rax, [rax+0F0h]
0x18002e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e71c  test    eax, eax
0x18002e71e  jnz     short loc_18002E72A
0x18002e720  mov     eax, 80070057h
0x18002e725  jmp     loc_18002EA2E
0x18002e72a  mov     edi, [rbx+80h]
0x18002e730  cmp     [r15+8], r12d
0x18002e734  jnz     loc_18002E817
0x18002e73a  test    edi, edi
0x18002e73c  jz      loc_18002E7F0
0x18002e742  xor     edx, edx; Val
0x18002e744  mov     [rbp+57h+hProcess], r12
0x18002e748  lea     rcx, [rbp+57h+var_80]; void *
0x18002e74c  lea     r8d, [rdx+40h]; Size
0x18002e750  call    memset_0
0x18002e755  mov     r8, [rbx+50h]; HWND
0x18002e759  lea     r9, [rbp+57h+var_80]; struct tagCOMBOBOXINFO *
0x18002e75d  mov     edx, [rbx+44h]; unsigned int
0x18002e760  mov     ecx, [rbx+64h]; unsigned int
0x18002e763  call    ?MyGetComboBoxInfo@@YAHKKPEAUHWND__@@PEAUtagCOMBOBOXINFO@@@Z; MyGetComboBoxInfo(ulong,ulong,HWND__ *,tagCOMBOBOXINFO *)
0x18002e768  test    eax, eax
0x18002e76a  jz      short loc_18002E7E6
0x18002e76c  mov     r8, [rbp+57h+var_80.hwndCombo]
0x18002e770  lea     rax, [rbp+57h+hProcess]
0x18002e774  mov     edx, [rbx+44h]
0x18002e777  mov     r9d, 0FFFFFFFCh
0x18002e77d  mov     ecx, [rbx+64h]
0x18002e780  mov     [rsp+100h+var_D8], rax
0x18002e785  lea     rax, IID_IAccessible
0x18002e78c  mov     [rsp+100h+lpNumberOfBytesRead], rax
0x18002e791  mov     [rbp+57h+hProcess], r12
0x18002e795  call    AccessibleObjectFromWindowTimeout
0x18002e79a  test    eax, eax
0x18002e79c  js      short loc_18002E7E6
0x18002e79e  mov     rcx, [rbp+57h+hProcess]
0x18002e7a2  test    rcx, rcx
0x18002e7a5  jz      short loc_18002E7E6
0x18002e7a7  mov     rax, [rcx]
0x18002e7aa  lea     rdx, [rbp+57h+var_A0]
0x18002e7ae  movups  xmm0, xmmword ptr [r15]
0x18002e7b2  mov     r8, rsi
0x18002e7b5  movsd   xmm1, qword ptr [r15+10h]
0x18002e7bb  mov     rax, [rax+50h]
0x18002e7bf  movaps  xmmword ptr [rbp+57h+var_A0], xmm0
0x18002e7c3  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18002e7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7cd  mov     rcx, [rbp+57h+hProcess]
0x18002e7d1  mov     ebx, eax
0x18002e7d3  mov     rdx, [rcx]
0x18002e7d6  mov     rax, [rdx+10h]
0x18002e7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7df  mov     eax, ebx
0x18002e7e1  jmp     loc_18002EA2E
0x18002e7e6  mov     eax, 1
0x18002e7eb  jmp     loc_18002EA2E
0x18002e7f0  movups  xmm0, xmmword ptr [r15]
0x18002e7f4  lea     rdx, [rbp+57h+var_A0]; struct tagVARIANT
0x18002e7f8  mov     r8, rsi; unsigned __int16 **
0x18002e7fb  movsd   xmm1, qword ptr [r15+10h]
0x18002e801  mov     rcx, rbx; this
0x18002e804  movaps  xmmword ptr [rbp+57h+var_A0], xmm0
0x18002e808  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18002e80d  call    ?get_accName@CClient@@UEAAJUtagVARIANT@@PEAPEAG@Z; CClient::get_accName(tagVARIANT,ushort * *)
0x18002e812  jmp     loc_18002EA2E
0x18002e817  xor     edx, edx; Val
0x18002e819  lea     rcx, [rbp+57h+var_80]; void *
0x18002e81d  lea     r8d, [rdx+40h]; Size
0x18002e821  call    memset_0
0x18002e826  test    edi, edi
0x18002e828  jz      short loc_18002E86A
0x18002e82a  mov     r8, [rbx+50h]; HWND
0x18002e82e  lea     r9, [rbp+57h+var_80]; struct tagCOMBOBOXINFO *
0x18002e832  mov     edx, [rbx+44h]; unsigned int
0x18002e835  mov     ecx, [rbx+64h]; unsigned int
0x18002e838  call    ?MyGetComboBoxInfo@@YAHKKPEAUHWND__@@PEAUtagCOMBOBOXINFO@@@Z; MyGetComboBoxInfo(ulong,ulong,HWND__ *,tagCOMBOBOXINFO *)
0x18002e83d  test    eax, eax
0x18002e83f  jz      short loc_18002E86A
0x18002e841  mov     r13, [rbp+57h+var_80.hwndCombo]
0x18002e845  mov     rcx, r13; hWnd
0x18002e848  call    ?IsInComboEx@@YAPEAUHWND__@@PEAU1@@Z; IsInComboEx(HWND__ *)
0x18002e84d  test    rax, rax
0x18002e850  mov     edi, r12d
0x18002e853  mov     r9d, 149h
0x18002e859  setnz   dil
0x18002e85d  cmovnz  r13, rax
0x18002e861  mov     dword ptr [rbp+57h+var_B8], edi
0x18002e864  lea     r14d, [r9-1]
0x18002e868  jmp     short loc_18002E87C
0x18002e86a  mov     r13, [rbx+50h]
0x18002e86e  mov     r9d, 18Ah; unsigned int
0x18002e874  mov     dword ptr [rbp+57h+var_B8], r12d
0x18002e878  lea     r14d, [r9-1]
0x18002e87c  mov     eax, [r15+8]
0x18002e880  mov     r8, r13; HWND
0x18002e883  dec     eax
0x18002e885  mov     [rbp+57h+hProcess], r12
0x18002e889  movsxd  rcx, eax
0x18002e88c  xor     edx, edx; bool
0x18002e88e  lea     rax, [rbp+57h+hProcess]
0x18002e892  mov     [rsp+100h+var_D0], rax; __int64 *
0x18002e897  mov     [rsp+100h+var_D8], r12; __int64
0x18002e89c  mov     [rsp+100h+lpNumberOfBytesRead], rcx; unsigned __int64
0x18002e8a1  mov     rcx, rbx; this
0x18002e8a4  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002e8a9  test    eax, eax
0x18002e8ab  js      loc_18002EA2E
0x18002e8b1  mov     esi, 400h
0x18002e8b6  mov     ecx, 0FFFFFFFFh
0x18002e8bb  cmp     dword ptr [rbp+57h+hProcess], esi
0x18002e8be  jb      short loc_18002E8D3
0x18002e8c0  mov     esi, dword ptr [rbp+57h+hProcess]
0x18002e8c3  cmp     esi, ecx
0x18002e8c5  jz      loc_18002EA2C
0x18002e8cb  test    esi, esi
0x18002e8cd  js      loc_18002EAF4
0x18002e8d3  lea     eax, [rsi+1]
0x18002e8d6  cmp     eax, esi
0x18002e8d8  jb      loc_18002EAF4
0x18002e8de  mov     r12d, eax
0x18002e8e1  add     r12, r12
0x18002e8e4  cmp     r12, rcx
0x18002e8e7  ja      loc_18002EAF4
0x18002e8ed  mov     r9d, [rbx+80h]; int
0x18002e8f4  mov     r8, [rbx+50h]; HWND
0x18002e8f8  mov     edx, [rbx+44h]; unsigned int
0x18002e8fb  mov     ecx, [rbx+64h]; unsigned int
0x18002e8fe  mov     dword ptr [rsp+100h+lpNumberOfBytesRead], r9d; int
0x18002e903  call    ?IsTridentControl@@YAHKKPEAUHWND__@@HH@Z; IsTridentControl(ulong,ulong,HWND__ *,int,int)
0x18002e908  test    eax, eax
0x18002e90a  jz      loc_18002EA55
0x18002e910  mov     [rbp+57h+hProcess], 0
0x18002e918  cmp     r14d, 189h
0x18002e91f  jnz     short loc_18002E929
0x18002e921  mov     r14d, 589h
0x18002e927  jmp     short loc_18002E939
0x18002e929  cmp     r14d, 148h
0x18002e930  mov     eax, 548h
0x18002e935  cmovz   r14d, eax
0x18002e939  lea     r8, [rbp+57h+hProcess]; void **
0x18002e93d  mov     rdx, r13; HWND
0x18002e940  mov     ecx, r12d; dwSize
0x18002e943  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002e948  mov     rdi, rax
0x18002e94b  test    rax, rax
0x18002e94e  jz      short loc_18002E979
0x18002e950  mov     eax, r12d
0x18002e953  mov     ecx, 40h ; '@'; uFlags
0x18002e958  mov     edx, r12d; uBytes
0x18002e95b  mov     [rbp+57h+nSize], rax
0x18002e95f  call    cs:__imp_LocalAlloc
0x18002e965  mov     r12, rax
0x18002e968  test    rax, rax
0x18002e96b  jnz     short loc_18002E983
0x18002e96d  mov     rdx, [rbp+57h+hProcess]; hProcess
0x18002e971  mov     rcx, rdi; lpAddress
0x18002e974  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002e979  mov     eax, 8007000Eh
0x18002e97e  jmp     loc_18002EA2E
0x18002e983  mov     eax, [r15+8]
0x18002e987  mov     r9d, r14d; unsigned int
0x18002e98a  dec     eax
0x18002e98c  mov     [rbp+57h+var_B8], 0
0x18002e994  movsxd  rcx, eax
0x18002e997  mov     r8, r13; HWND
0x18002e99a  lea     rax, [rbp+57h+var_B8]
0x18002e99e  xor     edx, edx; bool
0x18002e9a0  mov     [rsp+100h+var_D0], rax; __int64 *
0x18002e9a5  mov     [rsp+100h+var_D8], rdi; __int64
0x18002e9aa  mov     [rsp+100h+lpNumberOfBytesRead], rcx; unsigned __int64
0x18002e9af  mov     rcx, rbx; this
0x18002e9b2  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002e9b7  mov     ebx, eax
0x18002e9b9  test    eax, eax
0x18002e9bb  js      short loc_18002E9C7
0x18002e9bd  cmp     dword ptr [rbp+57h+var_B8], esi
0x18002e9c0  jbe     short loc_18002E9E1
0x18002e9c2  mov     ebx, 80004005h
0x18002e9c7  mov     rdx, [rbp+57h+hProcess]; hProcess
0x18002e9cb  mov     rcx, rdi; lpAddress
0x18002e9ce  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002e9d3  mov     rcx, r12; hMem
0x18002e9d6  call    cs:__imp_LocalFree
0x18002e9dc  jmp     loc_18002E7DF
0x18002e9e1  mov     r9, [rbp+57h+nSize]; nSize
0x18002e9e5  mov     r8, r12; lpBuffer
0x18002e9e8  mov     rcx, [rbp+57h+hProcess]; hProcess
0x18002e9ec  mov     rdx, rdi; lpBaseAddress
0x18002e9ef  mov     [rsp+100h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18002e9f8  call    cs:__imp_ReadProcessMemory
0x18002e9fe  mov     ecx, esi
0x18002ea00  xor     eax, eax
0x18002ea02  mov     [r12+rcx*2], ax
0x18002ea07  mov     rcx, r12; psz
0x18002ea0a  call    cs:__imp_SysAllocString
0x18002ea10  mov     rcx, [rbp+57h+var_B0]
0x18002ea14  mov     rdx, [rbp+57h+hProcess]; hProcess
0x18002ea18  mov     [rcx], rax
0x18002ea1b  mov     rcx, rdi; lpAddress
0x18002ea1e  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002ea23  mov     rcx, r12; hMem
0x18002ea26  call    cs:__imp_LocalFree
0x18002ea2c  xor     eax, eax
0x18002ea2e  mov     rcx, [rbp+57h+var_40]
0x18002ea32  xor     rcx, rsp; StackCookie
0x18002ea35  call    __security_check_cookie
0x18002ea3a  mov     rbx, [rsp+100h+arg_18]
0x18002ea42  add     rsp, 0D0h
0x18002ea49  pop     r15
0x18002ea4b  pop     r14
0x18002ea4d  pop     r13
0x18002ea4f  pop     r12
0x18002ea51  pop     rdi
0x18002ea52  pop     rsi
0x18002ea53  pop     rbp
0x18002ea54  retn
0x18002ea55  mov     rcx, [rbx+50h]; hWnd
0x18002ea59  mov     edx, 0FFFFFFF0h; nIndex
0x18002ea5e  call    cs:__imp_GetWindowLongW
0x18002ea64  mov     edx, r12d; uBytes
0x18002ea67  mov     ecx, 40h ; '@'; uFlags
0x18002ea6c  mov     dword ptr [rbp+57h+hProcess], eax
0x18002ea6f  call    cs:__imp_LocalAlloc
0x18002ea75  xor     r12d, r12d
0x18002ea78  mov     rdi, rax
0x18002ea7b  test    rax, rax
0x18002ea7e  jz      loc_18002E979
0x18002ea84  cmp     dword ptr [rbp+57h+var_B8], r12d
0x18002ea88  jz      short loc_18002EAC0
0x18002ea8a  mov     eax, [r15+8]
0x18002ea8e  mov     r9d, r14d; unsigned int
0x18002ea91  dec     eax
0x18002ea93  mov     [rsp+100h+var_D0], r12; __int64 *
0x18002ea98  movsxd  rcx, eax
0x18002ea9b  mov     r8, r13; HWND
0x18002ea9e  mov     [rsp+100h+var_D8], rdi; __int64
0x18002eaa3  xor     edx, edx; bool
0x18002eaa5  mov     [rsp+100h+lpNumberOfBytesRead], rcx; unsigned __int64
0x18002eaaa  mov     rcx, rbx; this
0x18002eaad  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002eab2  mov     ebx, eax
0x18002eab4  test    eax, eax
0x18002eab6  jns     short loc_18002EAD5
0x18002eab8  mov     rcx, rdi
0x18002eabb  jmp     loc_18002E9D6
0x18002eac0  mov     eax, dword ptr [rbp+57h+hProcess]
0x18002eac3  test    al, 30h
0x18002eac5  setnz   cl
0x18002eac8  test    al, 40h
0x18002eaca  setz    al
0x18002eacd  test    al, cl
0x18002eacf  jz      short loc_18002EA8A
0x18002ead1  mov     [rdi], r12w
0x18002ead5  mov     ecx, esi
0x18002ead7  mov     [rdi+rcx*2], r12w
0x18002eadc  mov     rcx, rdi; psz
0x18002eadf  call    cs:__imp_SysAllocString
0x18002eae5  mov     rcx, [rbp+57h+var_B0]
0x18002eae9  mov     [rcx], rax
0x18002eaec  mov     rcx, rdi
0x18002eaef  jmp     loc_18002EA26
0x18002eaf4  mov     eax, 80070216h
0x18002eaf9  jmp     loc_18002EA2E
```
