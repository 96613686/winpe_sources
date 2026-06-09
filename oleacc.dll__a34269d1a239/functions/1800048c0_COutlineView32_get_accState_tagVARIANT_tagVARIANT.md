# COutlineView32::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x1800048c0`
- end: `0x180004b81`
- name: `?get_accState@COutlineView32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `705`
- prototype: `__int64 __fastcall(struct IAccessible *this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800048c0`
- `0x180005ca0`
- `0x18000612c`
- `0x180006510`
- `0x180006c58`
- `0x180007530`
- `0x180007598`
- `0x18000771c`
- `0x18000d2b0`
- `0x180019d38`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180004a46`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180004a46`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800049c3`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800049eb`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180004a0c`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800049c3`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800049eb`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180004a0c`
- `USER32!SendMessageW` at `0x180004a21`
- `USER32!SendMessageW` at `0x180004ab9`
- `USER32!SendMessageW` at `0x180004a21`
- `USER32!SendMessageW` at `0x180004ab9`
- `USER32!GetWindowLongW` at `0x180004aa2`
- `USER32!GetWindowLongW` at `0x180004aa2`

## pseudocode

```c
__int64 __fastcall COutlineView32::get_accState(struct IAccessible *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  struct IAccessibleVtbl *lpVtbl; // rax
  ULONG (__stdcall *Release)(IAccessible *); // rax
  WPARAM Lo; // rdx
  IRecordInfo *pRecInfo; // xmm1_8
  void *v11; // rax
  LPARAM v12; // r14
  char v13; // cl
  struct IAccessibleVtbl *v14; // rbx
  HWND Focus; // rax
  LONG lVal; // eax
  LONG v17; // eax
  __int16 WindowLongW; // bx
  int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // r8d
  struct IAccessibleVtbl *v22; // rcx
  struct IAccessibleVtbl *v23; // rcx
  int v24; // [rsp+28h] [rbp-61h]
  struct _TREEITEM *v25; // [rsp+40h] [rbp-49h] BYREF
  int v26[6]; // [rsp+48h] [rbp-41h] BYREF
  struct tagVARIANT v27; // [rsp+60h] [rbp-29h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h] BYREF
  __int128 v29; // [rsp+90h] [rbp+7h]
  __int128 v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+B0h] [rbp+27h]
  unsigned int Buffer; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v33; // [rsp+100h] [rbp+77h] BYREF
  HANDLE hProcess; // [rsp+108h] [rbp+7Fh] BYREF

  hProcess = 0;
  v31 = 0;
  a3->vt = 0;
  lpVtbl = this->lpVtbl;
  v28 = 0;
  Release = lpVtbl[1].Release;
  v29 = 0;
  v30 = 0;
  if ( ((unsigned int (__fastcall *)(struct IAccessible *))Release)(this) )
  {
    Lo = a2->cyVal.Lo;
    if ( !(_DWORD)Lo )
    {
      pRecInfo = a2->pRecInfo;
      *(_OWORD *)&v27.vt = *(_OWORD *)&a2->vt;
      v27.pRecInfo = pRecInfo;
      return CClient::get_accState((CClient *)this, &v27, a3);
    }
    v25 = TVItemFromChildID((HWND)this[10].lpVtbl, Lo);
    if ( v25 )
    {
      a3->vt = 3;
      a3->lVal = 0x100000;
      if ( IsClippedByWindow(this, a2, (HWND)this[10].lpVtbl) )
        a3->lVal |= 0x18000u;
      v11 = SharedAlloc(0x38u, (HWND)this[10].lpVtbl, &hProcess);
      v12 = (LPARAM)v11;
      if ( !v11 )
        return 2147942414LL;
      Buffer = 72;
      WriteProcessMemory(hProcess, v11, &Buffer, 4u, 0);
      Buffer = 65280;
      WriteProcessMemory(hProcess, (LPVOID)(v12 + 20), &Buffer, 4u, 0);
      WriteProcessMemory(hProcess, (LPVOID)(v12 + 8), &v25, 8u, 0);
      if ( !(unsigned int)SendMessageW((HWND)this[10].lpVtbl, 0x113Eu, 0, v12) )
        goto LABEL_29;
      ReadProcessMemory(hProcess, (LPCVOID)v12, &v28, 0x38u, 0);
      v13 = v29;
      if ( (v29 & 2) != 0 )
      {
        a3->lVal |= 2u;
        v14 = this[10].lpVtbl;
        Focus = MyGetFocus();
        v13 = v29;
        if ( Focus == (HWND)v14 )
          a3->lVal |= 4u;
      }
      a3->lVal |= 0x200000u;
      lVal = a3->lVal;
      if ( (v13 & 8) != 0 )
      {
        lVal |= 0x80u;
        a3->lVal = lVal;
      }
      if ( (v13 & 0xA0) != 0 )
      {
        v17 = lVal | 0x200;
      }
      else
      {
        if ( !HIDWORD(v30) )
        {
LABEL_20:
          WindowLongW = GetWindowLongW((HWND)this[10].lpVtbl, -16);
          if ( (SendMessageW((HWND)this[10].lpVtbl, 0x112Du, 0, 0) & 0x380) != 0 || (WindowLongW & 0x100) != 0 )
          {
            v19 = v29 & 0xF000;
            if ( v19 == 0x2000 )
            {
              a3->lVal |= 0x10u;
            }
            else if ( v19 == 12288 )
            {
              a3->lVal |= 0x20u;
            }
          }
          if ( (unsigned int)TVGetImageIndex((HWND)this[10].lpVtbl, v25, v26) )
          {
            v22 = this[10].lpVtbl;
            Buffer = 0;
            *(GUID *)&v27.vt = PROPID_ACC_STATEMAP;
            if ( (unsigned int)CheckDWORDMap((HWND)v22, v20, v21, (struct _GUID *)&v27, v26, v24, &Buffer)
              || (v23 = this[10].lpVtbl, v33 = 0, (unsigned int)GetStateImageMapEnt((HWND)v23, v26[0], &Buffer, &v33)) )
            {
              a3->lVal |= Buffer;
            }
          }
LABEL_29:
          SharedFree((void *)v12, hProcess);
          return 0;
        }
        v17 = lVal | 0x400;
      }
      a3->lVal = v17;
      goto LABEL_20;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800048c0  push    rbp
0x1800048c2  push    rbx
0x1800048c3  push    rsi
0x1800048c4  push    rdi
0x1800048c5  push    r14
0x1800048c7  lea     rbp, [rsp-37h]
0x1800048cc  sub     rsp, 0C0h
0x1800048d3  xor     eax, eax
0x1800048d5  mov     [rbp+57h+hProcess], 0
0x1800048dd  xorps   xmm0, xmm0
0x1800048e0  mov     [rbp+57h+var_30], rax
0x1800048e4  mov     [r8], ax
0x1800048e8  mov     rdi, r8
0x1800048eb  mov     rax, [rcx]
0x1800048ee  mov     rbx, rdx
0x1800048f1  mov     rsi, rcx
0x1800048f4  movups  [rbp+57h+var_60], xmm0
0x1800048f8  mov     rax, [rax+0F0h]
0x1800048ff  movups  [rbp+57h+var_50], xmm0
0x180004903  movups  [rbp+57h+var_40], xmm0
0x180004907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490c  test    eax, eax
0x18000490e  jz      loc_180004B6E
0x180004914  mov     edx, [rbx+8]; wParam
0x180004917  test    edx, edx
0x180004919  jnz     short loc_180004940
0x18000491b  movups  xmm0, xmmword ptr [rbx]
0x18000491e  lea     rdx, [rbp+57h+var_80]; struct tagVARIANT
0x180004922  mov     r8, rdi; struct tagVARIANT *
0x180004925  movsd   xmm1, qword ptr [rbx+10h]
0x18000492a  mov     rcx, rsi; this
0x18000492d  movaps  xmmword ptr [rbp+57h+var_80], xmm0
0x180004931  movsd   qword ptr [rbp+57h+var_80+10h], xmm1
0x180004936  call    ?get_accState@CClient@@UEAAJUtagVARIANT@@PEAU2@@Z; CClient::get_accState(tagVARIANT,tagVARIANT *)
0x18000493b  jmp     loc_180004B73
0x180004940  mov     rcx, [rsi+50h]; HWND
0x180004944  call    ?TVItemFromChildID@@YAPEAU_TREEITEM@@PEAUHWND__@@K@Z; TVItemFromChildID(HWND__ *,ulong)
0x180004949  mov     [rbp+57h+var_A0], rax
0x18000494d  test    rax, rax
0x180004950  jz      loc_180004B6E
0x180004956  mov     word ptr [rdi], 3
0x18000495b  mov     rdx, rbx; struct tagVARIANT *
0x18000495e  mov     dword ptr [rdi+8], 100000h
0x180004965  mov     rcx, rsi; struct IAccessible *
0x180004968  mov     r8, [rsi+50h]; HWND
0x18000496c  call    ?IsClippedByWindow@@YAHPEAUIAccessible@@AEAUtagVARIANT@@PEAUHWND__@@@Z; IsClippedByWindow(IAccessible *,tagVARIANT &,HWND__ *)
0x180004971  test    eax, eax
0x180004973  jz      short loc_18000497C
0x180004975  or      dword ptr [rdi+8], 18000h
0x18000497c  mov     rdx, [rsi+50h]; HWND
0x180004980  lea     r8, [rbp+57h+hProcess]; void **
0x180004984  mov     ebx, 38h ; '8'
0x180004989  mov     ecx, ebx; dwSize
0x18000498b  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180004990  mov     r14, rax
0x180004993  test    rax, rax
0x180004996  jnz     short loc_1800049A2
0x180004998  mov     eax, 8007000Eh
0x18000499d  jmp     loc_180004B73
0x1800049a2  mov     rcx, [rbp+57h+hProcess]; hProcess
0x1800049a6  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800049aa  mov     r9d, 4; nSize
0x1800049b0  mov     [rbp+57h+Buffer], 48h ; 'H'
0x1800049b7  mov     rdx, r14; lpBaseAddress
0x1800049ba  mov     [rsp+0E0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800049c3  call    cs:__imp_WriteProcessMemory
0x1800049c9  mov     rcx, [rbp+57h+hProcess]; hProcess
0x1800049cd  lea     rdx, [r14+14h]; lpBaseAddress
0x1800049d1  mov     r9d, 4; nSize
0x1800049d7  mov     [rbp+57h+Buffer], 0FF00h
0x1800049de  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800049e2  mov     [rsp+0E0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800049eb  call    cs:__imp_WriteProcessMemory
0x1800049f1  mov     rcx, [rbp+57h+hProcess]; hProcess
0x1800049f5  lea     rdx, [r14+8]; lpBaseAddress
0x1800049f9  mov     r9d, 8; nSize
0x1800049ff  mov     [rsp+0E0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180004a08  lea     r8, [rbp+57h+var_A0]; lpBuffer
0x180004a0c  call    cs:__imp_WriteProcessMemory
0x180004a12  mov     rcx, [rsi+50h]; hWnd
0x180004a16  mov     r9, r14; lParam
0x180004a19  xor     r8d, r8d; wParam
0x180004a1c  mov     edx, 113Eh; Msg
0x180004a21  call    cs:__imp_SendMessageW
0x180004a27  test    eax, eax
0x180004a29  jz      loc_180004B5E
0x180004a2f  mov     rcx, [rbp+57h+hProcess]; hProcess
0x180004a33  lea     r8, [rbp+57h+var_60]; lpBuffer
0x180004a37  mov     r9, rbx; nSize
0x180004a3a  mov     [rsp+0E0h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180004a43  mov     rdx, r14; lpBaseAddress
0x180004a46  call    cs:__imp_ReadProcessMemory
0x180004a4c  mov     ecx, dword ptr [rbp+57h+var_50]
0x180004a4f  test    cl, 2
0x180004a52  jz      short loc_180004A6D
0x180004a54  or      dword ptr [rdi+8], 2
0x180004a58  mov     rbx, [rsi+50h]
0x180004a5c  call    ?MyGetFocus@@YAPEAUHWND__@@XZ; MyGetFocus(void)
0x180004a61  mov     ecx, dword ptr [rbp+57h+var_50]
0x180004a64  cmp     rax, rbx
0x180004a67  jnz     short loc_180004A6D
0x180004a69  or      dword ptr [rdi+8], 4
0x180004a6d  bts     dword ptr [rdi+8], 15h
0x180004a72  mov     eax, [rdi+8]
0x180004a75  test    cl, 8
0x180004a78  jz      short loc_180004A81
0x180004a7a  bts     eax, 7
0x180004a7e  mov     [rdi+8], eax
0x180004a81  test    cl, 0A0h
0x180004a84  jz      short loc_180004A8C
0x180004a86  bts     eax, 9
0x180004a8a  jmp     short loc_180004A96
0x180004a8c  cmp     dword ptr [rbp+57h+var_40+0Ch], 0
0x180004a90  jz      short loc_180004A99
0x180004a92  bts     eax, 0Ah
0x180004a96  mov     [rdi+8], eax
0x180004a99  mov     rcx, [rsi+50h]; hWnd
0x180004a9d  mov     edx, 0FFFFFFF0h; nIndex
0x180004aa2  call    cs:__imp_GetWindowLongW
0x180004aa8  mov     rcx, [rsi+50h]; hWnd
0x180004aac  xor     r9d, r9d; lParam
0x180004aaf  xor     r8d, r8d; wParam
0x180004ab2  mov     edx, 112Dh; Msg
0x180004ab7  mov     ebx, eax
0x180004ab9  call    cs:__imp_SendMessageW
0x180004abf  test    eax, 380h
0x180004ac4  setz    cl
0x180004ac7  bt      ebx, 8
0x180004acb  setnb   al
0x180004ace  test    al, cl
0x180004ad0  jnz     short loc_180004AF2
0x180004ad2  mov     eax, dword ptr [rbp+57h+var_50]
0x180004ad5  and     eax, 0F000h
0x180004ada  cmp     eax, 2000h
0x180004adf  jnz     short loc_180004AE7
0x180004ae1  or      dword ptr [rdi+8], 10h
0x180004ae5  jmp     short loc_180004AF2
0x180004ae7  cmp     eax, 3000h
0x180004aec  jnz     short loc_180004AF2
0x180004aee  or      dword ptr [rdi+8], 20h
0x180004af2  mov     rdx, [rbp+57h+var_A0]; struct _TREEITEM *
0x180004af6  lea     r8, [rbp+57h+var_98]; int *
0x180004afa  mov     rcx, [rsi+50h]; hWnd
0x180004afe  call    ?TVGetImageIndex@@YAHPEAUHWND__@@PEAU_TREEITEM@@QEAH@Z; TVGetImageIndex(HWND__ *,_TREEITEM *,int * const)
0x180004b03  test    eax, eax
0x180004b05  jz      short loc_180004B5E
0x180004b07  movups  xmm0, xmmword ptr cs:PROPID_ACC_STATEMAP.Data1
0x180004b0e  mov     rcx, [rsi+50h]; HWND
0x180004b12  lea     rax, [rbp+57h+Buffer]
0x180004b16  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x180004b1b  lea     r9, [rbp+57h+var_80]; struct _GUID *
0x180004b1f  lea     rax, [rbp+57h+var_98]
0x180004b23  mov     [rbp+57h+Buffer], 0
0x180004b2a  mov     [rsp+0E0h+lpNumberOfBytesWritten], rax; int *
0x180004b2f  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180004b34  call    ?CheckDWORDMap@@YAHPEAUHWND__@@KKU_GUID@@PEAHHPEAK@Z; CheckDWORDMap(HWND__ *,ulong,ulong,_GUID,int *,int,ulong *)
0x180004b39  test    eax, eax
0x180004b3b  jnz     short loc_180004B58
0x180004b3d  mov     edx, [rbp+57h+var_98]; int
0x180004b40  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x180004b44  mov     rcx, [rsi+50h]; HWND
0x180004b48  lea     r8, [rbp+57h+Buffer]; unsigned int *
0x180004b4c  mov     [rbp+57h+arg_10], eax
0x180004b4f  call    ?GetStateImageMapEnt@@YAHPEAUHWND__@@HPEAK1@Z; GetStateImageMapEnt(HWND__ *,int,ulong *,ulong *)
0x180004b54  test    eax, eax
0x180004b56  jz      short loc_180004B5E
0x180004b58  mov     eax, [rbp+57h+Buffer]
0x180004b5b  or      [rdi+8], eax
0x180004b5e  mov     rdx, [rbp+57h+hProcess]; hProcess
0x180004b62  mov     rcx, r14; lpAddress
0x180004b65  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180004b6a  xor     eax, eax
0x180004b6c  jmp     short loc_180004B73
0x180004b6e  mov     eax, 80070057h
0x180004b73  add     rsp, 0C0h
0x180004b7a  pop     r14
0x180004b7c  pop     rdi
0x180004b7d  pop     rsi
0x180004b7e  pop     rbx
0x180004b7f  pop     rbp
0x180004b80  retn
```
