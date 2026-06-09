# CscTransitionItemsOnline(HWND__ *,IShellItemArray *)

- ea: `0x1800440f4`
- end: `0x180044312`
- name: `?CscTransitionItemsOnline@@YAJPEAUHWND__@@PEAUIShellItemArray@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(HWND, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028d80`

## callees

- `0x18000c1e8`
- `0x180043d64`
- `0x180043d8c`
- `0x180043e68`
- `0x1800440f4`
- `0x180044318`
- `0x1800444b8`
- `0x180044588`
- `0x1800445f8`
- `0x1800446ec`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800442f4`

## pseudocode

```c
__int64 __fastcall CscTransitionItemsOnline(HWND a1, struct IShellItemArray *a2)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  unsigned int v4; // edi
  int v5; // ebx
  const unsigned __int16 **v6; // rsi
  _DWORD *v7; // rax
  _DWORD *v8; // r15
  unsigned int v9; // r14d
  struct IShellItem *v10; // r13
  struct IShellItemArrayVtbl *v11; // rax
  __int64 v12; // rax
  unsigned int i; // ecx
  _QWORD *v14; // rdi
  unsigned int v15; // edx
  unsigned int j; // edi
  _QWORD v18[3]; // [rsp+20h] [rbp-48h] BYREF
  int v19; // [rsp+38h] [rbp-30h]
  int v20; // [rsp+3Ch] [rbp-2Ch]
  _QWORD v21[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+50h] BYREF
  struct IShellItem *v24; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int16 **v25; // [rsp+C8h] [rbp+60h]

  lpVtbl = a2->lpVtbl;
  v4 = 0;
  v23 = 0;
  v5 = -2147467259;
  if ( ((int (__fastcall *)(struct IShellItemArray *, unsigned int *))lpVtbl->GetCount)(a2, &v23) >= 0 )
  {
    if ( v23 )
    {
      v18[1] = 0;
      v18[0] = &CCscUiComTaskContext::`vftable';
      v18[2] = 0;
      v19 = 2;
      v20 = -1;
      v24 = 0;
      v5 = CComTaskThread<CCscUiComTaskContext>::CreateInstance(v18, &v24);
      if ( v5 >= 0 )
      {
        v6 = (const unsigned __int16 **)CoTaskMemAlloc(8LL * v23);
        v7 = CoTaskMemAlloc(4LL * v23);
        v8 = v7;
        if ( v6 && v7 )
        {
          v9 = 0;
          v10 = v24;
          if ( v23 )
          {
            do
            {
              v11 = a2->lpVtbl;
              v24 = 0;
              if ( ((int (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v11->GetItemAt)(
                     a2,
                     v4,
                     &v24) >= 0 )
              {
                v25 = (unsigned __int16 **)&v6[v9];
                v5 = ConvertItemToUNCPath(v24, v25);
                if ( v5 >= 0 )
                {
                  v21[1] = 0;
                  v21[0] = &CTransitionCscScopeOnlineTask::`vftable';
                  v21[2] = *v25;
                  v21[3] = a1;
                  v5 = CComTaskThread<CCscUiComTaskContext>::DoTask(v10, v21);
                  v12 = v9++;
                  v8[v12] = v5;
                }
              }
              ++v4;
            }
            while ( v4 < v23 );
          }
          for ( i = 0; i < v9; ++i )
          {
            if ( (int)v8[i] < 0 )
            {
              v14 = operator new(0xC0u);
              if ( v14 )
              {
                *v14 = a1;
                v14[1] = 0;
                v14[22] = 0;
                *((_DWORD *)v14 + 46) = 0;
                v5 = CCscWorkOnlineErrorTaskDialog::Init((CCscWorkOnlineErrorTaskDialog *)v14, v6, v9);
                if ( v5 >= 0 )
                {
                  v5 = CCscWorkOnlineErrorTaskDialog::Run((CCscWorkOnlineErrorTaskDialog *)v14);
                  CCscWorkOnlineErrorTaskDialog::`scalar deleting destructor'((CCscWorkOnlineErrorTaskDialog *)v14, v15);
                }
              }
              else
              {
                v5 = -2147024882;
              }
              break;
            }
          }
          CComTaskThread<CCscUiComTaskContext>::TerminateThread(v10);
          CComTaskThread<CCscUiComTaskContext>::Release(v10);
          for ( j = 0; j < v9; ++j )
            CoTaskMemFree((LPVOID)v6[j]);
          CoTaskMemFree(v6);
          CoTaskMemFree(v8);
        }
        else
        {
          CoTaskMemFree(v6);
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800440f4  mov     [rsp-40h+arg_0], rcx
0x1800440f9  push    rbp
0x1800440fa  push    rbx
0x1800440fb  push    rsi
0x1800440fc  push    rdi
0x1800440fd  push    r12
0x1800440ff  push    r13
0x180044101  push    r14
0x180044103  push    r15
0x180044105  mov     rbp, rsp
0x180044108  sub     rsp, 68h
0x18004410c  mov     rax, [rdx]
0x18004410f  mov     r12, rdx
0x180044112  xor     edi, edi
0x180044114  lea     rdx, [rbp+arg_8]
0x180044118  mov     rcx, r12
0x18004411b  mov     [rbp+arg_8], edi
0x18004411e  mov     ebx, 80004005h
0x180044123  mov     rax, [rax+38h]
0x180044127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004412c  test    eax, eax
0x18004412e  js      loc_1800442FF
0x180044134  cmp     [rbp+arg_8], edi
0x180044137  jz      loc_1800442FF
0x18004413d  lea     rax, ??_7CCscUiComTaskContext@@6B@; const CCscUiComTaskContext::`vftable'
0x180044144  mov     [rbp+var_40], rdi
0x180044148  lea     rdx, [rbp+arg_10]
0x18004414c  mov     [rbp+var_48], rax
0x180044150  lea     rcx, [rbp+var_48]
0x180044154  mov     [rbp+var_38], rdi
0x180044158  mov     [rbp+var_30], 2
0x18004415f  mov     [rbp+var_2C], 0FFFFFFFFh
0x180044166  mov     [rbp+arg_10], rdi
0x18004416a  call    ?CreateInstance@?$CComTaskThread@VCCscUiComTaskContext@@@@SAJPEAVCCscUiComTaskContext@@PEAPEAV1@@Z; CComTaskThread<CCscUiComTaskContext>::CreateInstance(CCscUiComTaskContext *,CComTaskThread<CCscUiComTaskContext> * *)
0x18004416f  mov     ebx, eax
0x180044171  test    eax, eax
0x180044173  js      loc_1800442FF
0x180044179  mov     ecx, [rbp+arg_8]
0x18004417c  shl     rcx, 3; cb
0x180044180  call    cs:__imp_CoTaskMemAlloc
0x180044186  mov     ecx, [rbp+arg_8]
0x180044189  mov     rsi, rax
0x18004418c  shl     rcx, 2; cb
0x180044190  call    cs:__imp_CoTaskMemAlloc
0x180044196  mov     r15, rax
0x180044199  test    rsi, rsi
0x18004419c  jz      loc_1800442F1
0x1800441a2  test    rax, rax
0x1800441a5  jz      loc_1800442F1
0x1800441ab  mov     r14d, edi
0x1800441ae  mov     r13, [rbp+arg_10]
0x1800441b2  cmp     [rbp+arg_8], edi
0x1800441b5  jbe     loc_180044243
0x1800441bb  mov     rax, [r12]
0x1800441bf  lea     r8, [rbp+arg_10]
0x1800441c3  mov     edx, edi
0x1800441c5  mov     [rbp+arg_10], 0
0x1800441cd  mov     rcx, r12
0x1800441d0  mov     rax, [rax+40h]
0x1800441d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441d9  test    eax, eax
0x1800441db  js      short loc_180044238
0x1800441dd  mov     rcx, [rbp+arg_10]; struct IShellItem *
0x1800441e1  mov     eax, r14d
0x1800441e4  lea     rax, [rsi+rax*8]
0x1800441e8  mov     rdx, rax; unsigned __int16 **
0x1800441eb  mov     [rbp+arg_18], rax
0x1800441ef  call    ?ConvertItemToUNCPath@@YAJPEAUIShellItem@@PEAPEAG@Z; ConvertItemToUNCPath(IShellItem *,ushort * *)
0x1800441f4  mov     ebx, eax
0x1800441f6  test    eax, eax
0x1800441f8  js      short loc_180044238
0x1800441fa  lea     rax, ??_7CTransitionCscScopeOnlineTask@@6B@; const CTransitionCscScopeOnlineTask::`vftable'
0x180044201  mov     [rbp+var_20], 0
0x180044209  mov     [rbp+var_28], rax
0x18004420d  lea     rdx, [rbp+var_28]
0x180044211  mov     rax, [rbp+arg_18]
0x180044215  mov     rcx, r13
0x180044218  mov     rax, [rax]
0x18004421b  mov     [rbp+var_18], rax
0x18004421f  mov     rax, [rbp+arg_0]
0x180044223  mov     [rbp+var_10], rax
0x180044227  call    ?DoTask@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscUiComTaskContext@@@@@Z; CComTaskThread<CCscUiComTaskContext>::DoTask(CComTask<CCscUiComTaskContext> *)
0x18004422c  mov     ebx, eax
0x18004422e  mov     eax, r14d
0x180044231  inc     r14d
0x180044234  mov     [r15+rax*4], ebx
0x180044238  inc     edi
0x18004423a  cmp     edi, [rbp+arg_8]
0x18004423d  jb      loc_1800441BB
0x180044243  xor     r12d, r12d
0x180044246  mov     ecx, r12d
0x180044249  cmp     ecx, r14d
0x18004424c  jnb     short loc_1800442B2
0x18004424e  mov     eax, ecx
0x180044250  cmp     [r15+rax*4], r12d
0x180044254  jl      short loc_18004425A
0x180044256  inc     ecx
0x180044258  jmp     short loc_180044249
0x18004425a  mov     ecx, 0C0h; Size
0x18004425f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044264  mov     rdi, rax
0x180044267  test    rax, rax
0x18004426a  jz      short loc_1800442AD
0x18004426c  mov     rax, [rbp+arg_0]
0x180044270  mov     r8d, r14d; unsigned int
0x180044273  mov     rdx, rsi; unsigned __int16 **
0x180044276  mov     [rdi], rax
0x180044279  mov     rcx, rdi; this
0x18004427c  mov     [rdi+8], r12
0x180044280  mov     [rdi+0B0h], r12
0x180044287  mov     [rdi+0B8h], r12d
0x18004428e  call    ?Init@CCscWorkOnlineErrorTaskDialog@@QEAAJPEAPEBGK@Z; CCscWorkOnlineErrorTaskDialog::Init(ushort const * *,ulong)
0x180044293  mov     ebx, eax
0x180044295  test    eax, eax
0x180044297  js      short loc_1800442B2
0x180044299  mov     rcx, rdi; this
0x18004429c  call    ?Run@CCscWorkOnlineErrorTaskDialog@@QEAAJXZ; CCscWorkOnlineErrorTaskDialog::Run(void)
0x1800442a1  mov     rcx, rdi; this
0x1800442a4  mov     ebx, eax
0x1800442a6  call    ??_GCCscWorkOnlineErrorTaskDialog@@QEAAPEAXI@Z; CCscWorkOnlineErrorTaskDialog::`scalar deleting destructor'(uint)
0x1800442ab  jmp     short loc_1800442B2
0x1800442ad  mov     ebx, 8007000Eh
0x1800442b2  mov     rcx, r13
0x1800442b5  call    ?TerminateThread@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJXZ; CComTaskThread<CCscUiComTaskContext>::TerminateThread(void)
0x1800442ba  mov     rcx, r13; Block
0x1800442bd  call    ?Release@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAKXZ; CComTaskThread<CCscUiComTaskContext>::Release(void)
0x1800442c2  mov     edi, r12d
0x1800442c5  test    r14d, r14d
0x1800442c8  jz      short loc_1800442DD
0x1800442ca  mov     ecx, edi
0x1800442cc  mov     rcx, [rsi+rcx*8]; pv
0x1800442d0  call    cs:__imp_CoTaskMemFree
0x1800442d6  inc     edi
0x1800442d8  cmp     edi, r14d
0x1800442db  jb      short loc_1800442CA
0x1800442dd  mov     rcx, rsi; pv
0x1800442e0  call    cs:__imp_CoTaskMemFree
0x1800442e6  mov     rcx, r15; pv
0x1800442e9  call    cs:__imp_CoTaskMemFree
0x1800442ef  jmp     short loc_1800442FF
0x1800442f1  mov     rcx, rsi; pv
0x1800442f4  call    cs:__imp_CoTaskMemFree
0x1800442fa  mov     ebx, 8007000Eh
0x1800442ff  mov     eax, ebx
0x180044301  add     rsp, 68h
0x180044305  pop     r15
0x180044307  pop     r14
0x180044309  pop     r13
0x18004430b  pop     r12
0x18004430d  pop     rdi
0x18004430e  pop     rsi
0x18004430f  pop     rbx
0x180044310  pop     rbp
0x180044311  retn
```
