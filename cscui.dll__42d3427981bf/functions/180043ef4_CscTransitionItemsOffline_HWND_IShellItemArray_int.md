# CscTransitionItemsOffline(HWND__ *,IShellItemArray *,int *)

- ea: `0x180043ef4`
- end: `0x1800440ec`
- name: `?CscTransitionItemsOffline@@YAJPEAUHWND__@@PEAUIShellItemArray@@PEAH@Z`
- size: `504`
- prototype: `__int64 __fastcall(HWND, struct IShellItemArray *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028d80`

## callees

- `0x18000c1e8`
- `0x180043b38`
- `0x180043d3c`
- `0x180043d8c`
- `0x180043e68`
- `0x180043ef4`
- `0x180044318`
- `0x180044394`
- `0x180044588`
- `0x1800445c8`
- `0x1800446ec`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043f7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043f7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440ce`

## pseudocode

```c
__int64 __fastcall CscTransitionItemsOffline(HWND a1, struct IShellItemArray *a2, int *a3)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  struct IShellItemArray *v4; // r13
  int v6; // ebx
  const unsigned __int16 **v7; // r14
  __int64 v8; // rsi
  unsigned int i; // edi
  struct IShellItemArrayVtbl *v10; // rcx
  CCscWorkOfflineTaskDialog *v11; // rax
  CCscWorkOfflineTaskDialog *v12; // rax
  CCscWorkOfflineTaskDialog *v13; // rdi
  unsigned int v14; // edx
  __int64 j; // rdi
  struct IShellItem *v17; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v18[3]; // [rsp+28h] [rbp-48h] BYREF
  int v19; // [rsp+40h] [rbp-30h]
  int v20; // [rsp+44h] [rbp-2Ch]
  _QWORD v21[4]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+68h] [rbp-8h]
  unsigned int v25; // [rsp+C0h] [rbp+50h] BYREF
  void *Block; // [rsp+C8h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v4 = a2;
  *a3 = 0;
  v25 = 0;
  v6 = -2147467259;
  if ( ((int (__fastcall *)(struct IShellItemArray *, unsigned int *))lpVtbl->GetCount)(a2, &v25) >= 0 && v25 )
  {
    v18[1] = 0;
    v18[0] = &CCscUiComTaskContext::`vftable';
    v18[2] = 0;
    v19 = 2;
    v20 = -1;
    v7 = (const unsigned __int16 **)CoTaskMemAlloc(8LL * v25);
    if ( v7 )
    {
      v8 = 0;
      Block = 0;
      v6 = CComTaskThread<CCscUiComTaskContext>::CreateInstance(v18, &Block);
      if ( v6 >= 0 )
      {
        for ( i = 0; i < v25; ++i )
        {
          v10 = v4->lpVtbl;
          v17 = 0;
          if ( ((int (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v10->GetItemAt)(v4, i, &v17) >= 0 )
          {
            v6 = ConvertItemToUNCPath(v17, (unsigned __int16 **)&v7[v8]);
            if ( v6 >= 0 )
            {
              v21[0] = &CTransitionCscScopeOfflineTask::`vftable';
              v21[2] = v7[v8];
              v21[3] = a1;
              v21[1] = 0;
              v22 = 0;
              v6 = CComTaskThread<CCscUiComTaskContext>::DoTask(Block, v21);
              if ( v6 >= 0 )
                *a3 |= v22;
              v8 = (unsigned int)(v8 + 1);
            }
            v4 = a2;
          }
        }
        CComTaskThread<CCscUiComTaskContext>::TerminateThread(Block);
        CComTaskThread<CCscUiComTaskContext>::Release(Block);
        if ( *a3 )
        {
          v11 = (CCscWorkOfflineTaskDialog *)operator new(0x1C0u);
          if ( v11 && (v12 = CCscWorkOfflineTaskDialog::CCscWorkOfflineTaskDialog(v11, a1), (v13 = v12) != 0) )
          {
            v6 = CCscWorkOfflineTaskDialog::Init(v12, v7, v8);
            if ( v6 >= 0 )
            {
              v6 = CCscWorkOfflineTaskDialog::Run(v13);
              *a3 = *((_DWORD *)v13 + 111);
              CCscWorkOfflineTaskDialog::`scalar deleting destructor'(v13, v14);
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
      }
      for ( j = 0; (unsigned int)j < (unsigned int)v8; j = (unsigned int)(j + 1) )
        CoTaskMemFree((LPVOID)v7[j]);
      CoTaskMemFree(v7);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180043ef4  mov     [rsp-38h+arg_8], rdx
0x180043ef9  mov     [rsp-38h+arg_0], rcx
0x180043efe  push    rbp
0x180043eff  push    rbx
0x180043f00  push    rsi
0x180043f01  push    rdi
0x180043f02  push    r13
0x180043f04  push    r14
0x180043f06  push    r15
0x180043f08  mov     rbp, rsp
0x180043f0b  sub     rsp, 70h
0x180043f0f  mov     rax, [rdx]
0x180043f12  mov     r13, rdx
0x180043f15  lea     rdx, [rbp+arg_10]
0x180043f19  mov     dword ptr [r8], 0
0x180043f20  mov     rcx, r13
0x180043f23  mov     [rbp+arg_10], 0
0x180043f2a  mov     r15, r8
0x180043f2d  mov     ebx, 80004005h
0x180043f32  mov     rax, [rax+38h]
0x180043f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f3b  test    eax, eax
0x180043f3d  js      loc_1800440DB
0x180043f43  mov     eax, [rbp+arg_10]
0x180043f46  test    eax, eax
0x180043f48  jz      loc_1800440DB
0x180043f4e  lea     rcx, ??_7CCscUiComTaskContext@@6B@; const CCscUiComTaskContext::`vftable'
0x180043f55  mov     [rbp+var_40], 0
0x180043f5d  mov     [rbp+var_48], rcx
0x180043f61  mov     ecx, eax
0x180043f63  shl     rcx, 3; cb
0x180043f67  mov     [rbp+var_38], 0
0x180043f6f  mov     [rbp+var_30], 2
0x180043f76  mov     [rbp+var_2C], 0FFFFFFFFh
0x180043f7d  call    cs:__imp_CoTaskMemAlloc
0x180043f83  mov     r14, rax
0x180043f86  test    rax, rax
0x180043f89  jz      loc_1800440D6
0x180043f8f  xor     esi, esi
0x180043f91  lea     rdx, [rbp+Block]
0x180043f95  lea     rcx, [rbp+var_48]
0x180043f99  mov     [rbp+Block], rsi
0x180043f9d  call    ?CreateInstance@?$CComTaskThread@VCCscUiComTaskContext@@@@SAJPEAVCCscUiComTaskContext@@PEAPEAV1@@Z; CComTaskThread<CCscUiComTaskContext>::CreateInstance(CCscUiComTaskContext *,CComTaskThread<CCscUiComTaskContext> * *)
0x180043fa2  mov     ebx, eax
0x180043fa4  test    eax, eax
0x180043fa6  js      loc_1800440B5
0x180043fac  xor     edi, edi
0x180043fae  cmp     [rbp+arg_10], esi
0x180043fb1  jbe     loc_180044044
0x180043fb7  mov     rcx, [r13+0]
0x180043fbb  lea     r8, [rbp+var_50]
0x180043fbf  mov     edx, edi
0x180043fc1  mov     [rbp+var_50], 0
0x180043fc9  mov     rax, [rcx+40h]
0x180043fcd  mov     rcx, r13
0x180043fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fd5  test    eax, eax
0x180043fd7  js      short loc_180044039
0x180043fd9  mov     rcx, [rbp+var_50]; struct IShellItem *
0x180043fdd  lea     r13, [r14+rsi*8]
0x180043fe1  mov     rdx, r13; unsigned __int16 **
0x180043fe4  call    ?ConvertItemToUNCPath@@YAJPEAUIShellItem@@PEAPEAG@Z; ConvertItemToUNCPath(IShellItem *,ushort * *)
0x180043fe9  mov     ebx, eax
0x180043feb  test    eax, eax
0x180043fed  js      short loc_180044035
0x180043fef  mov     rcx, [rbp+Block]
0x180043ff3  lea     rax, ??_7CTransitionCscScopeOfflineTask@@6B@; const CTransitionCscScopeOfflineTask::`vftable'
0x180043ffa  mov     [rbp+var_28], rax
0x180043ffe  lea     rdx, [rbp+var_28]
0x180044002  mov     rax, [r13+0]
0x180044006  mov     [rbp+var_18], rax
0x18004400a  mov     rax, [rbp+arg_0]
0x18004400e  mov     [rbp+var_10], rax
0x180044012  mov     [rbp+var_20], 0
0x18004401a  mov     [rbp+var_8], 0
0x180044022  call    ?DoTask@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscUiComTaskContext@@@@@Z; CComTaskThread<CCscUiComTaskContext>::DoTask(CComTask<CCscUiComTaskContext> *)
0x180044027  mov     ebx, eax
0x180044029  test    eax, eax
0x18004402b  js      short loc_180044033
0x18004402d  mov     eax, dword ptr [rbp+var_8]
0x180044030  or      [r15], eax
0x180044033  inc     esi
0x180044035  mov     r13, [rbp+arg_8]
0x180044039  inc     edi
0x18004403b  cmp     edi, [rbp+arg_10]
0x18004403e  jb      loc_180043FB7
0x180044044  mov     rcx, [rbp+Block]
0x180044048  call    ?TerminateThread@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJXZ; CComTaskThread<CCscUiComTaskContext>::TerminateThread(void)
0x18004404d  mov     rcx, [rbp+Block]; Block
0x180044051  call    ?Release@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAKXZ; CComTaskThread<CCscUiComTaskContext>::Release(void)
0x180044056  cmp     dword ptr [r15], 0
0x18004405a  jz      short loc_1800440B5
0x18004405c  mov     ecx, 1C0h; Size
0x180044061  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044066  test    rax, rax
0x180044069  jz      short loc_1800440B0
0x18004406b  mov     rdx, [rbp+arg_0]; HWND
0x18004406f  mov     rcx, rax; this
0x180044072  call    ??0CCscWorkOfflineTaskDialog@@QEAA@PEAUHWND__@@@Z; CCscWorkOfflineTaskDialog::CCscWorkOfflineTaskDialog(HWND__ *)
0x180044077  mov     rdi, rax
0x18004407a  test    rax, rax
0x18004407d  jz      short loc_1800440B0
0x18004407f  mov     r8d, esi; unsigned int
0x180044082  mov     rdx, r14; unsigned __int16 **
0x180044085  mov     rcx, rax; this
0x180044088  call    ?Init@CCscWorkOfflineTaskDialog@@QEAAJPEAPEBGK@Z; CCscWorkOfflineTaskDialog::Init(ushort const * *,ulong)
0x18004408d  mov     ebx, eax
0x18004408f  test    eax, eax
0x180044091  js      short loc_1800440B5
0x180044093  mov     rcx, rdi; this
0x180044096  call    ?Run@CCscWorkOfflineTaskDialog@@QEAAJXZ; CCscWorkOfflineTaskDialog::Run(void)
0x18004409b  mov     ebx, eax
0x18004409d  mov     rcx, rdi; this
0x1800440a0  mov     eax, [rdi+1BCh]
0x1800440a6  mov     [r15], eax
0x1800440a9  call    ??_GCCscWorkOfflineTaskDialog@@QEAAPEAXI@Z; CCscWorkOfflineTaskDialog::`scalar deleting destructor'(uint)
0x1800440ae  jmp     short loc_1800440B5
0x1800440b0  mov     ebx, 8007000Eh
0x1800440b5  xor     edi, edi
0x1800440b7  test    esi, esi
0x1800440b9  jz      short loc_1800440CB
0x1800440bb  mov     rcx, [r14+rdi*8]; pv
0x1800440bf  call    cs:__imp_CoTaskMemFree
0x1800440c5  inc     edi
0x1800440c7  cmp     edi, esi
0x1800440c9  jb      short loc_1800440BB
0x1800440cb  mov     rcx, r14; pv
0x1800440ce  call    cs:__imp_CoTaskMemFree
0x1800440d4  jmp     short loc_1800440DB
0x1800440d6  mov     ebx, 8007000Eh
0x1800440db  mov     eax, ebx
0x1800440dd  add     rsp, 70h
0x1800440e1  pop     r15
0x1800440e3  pop     r14
0x1800440e5  pop     r13
0x1800440e7  pop     rdi
0x1800440e8  pop     rsi
0x1800440e9  pop     rbx
0x1800440ea  pop     rbp
0x1800440eb  retn
```
