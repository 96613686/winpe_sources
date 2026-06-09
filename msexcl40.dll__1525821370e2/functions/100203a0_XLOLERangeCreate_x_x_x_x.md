# XLOLERangeCreate(x,x,x,x)

- ea: `0x100203a0`
- end: `0x100204d6`
- name: `_XLOLERangeCreate@16`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1001bb70`

## callees

- `0x100203a0`
- `0x10021260`
- `0x10021330`
- `0x10021fe0`
- `0x10035510`
- `0x100358c5`
- `0x10035e9f`

## pseudocode

```c
int __fastcall XLOLERangeCreate(int a1, struct ExcelRange **a2, unsigned int a3, int a4)
{
  DispatchDriver *v4; // edi
  ExcelRange *v5; // ecx
  DispatchDriver *v6; // ebx
  ExcelRange *v7; // ecx
  DispatchDriver *v8; // esi
  ExcelRange *v9; // ecx
  struct ExcelRange *v10; // eax
  int v12; // [esp+0h] [ebp-30h] BYREF
  struct ExcelRange **v13; // [esp+10h] [ebp-20h]
  CHAR v14[4]; // [esp+14h] [ebp-1Ch] BYREF
  CHAR v15[4]; // [esp+18h] [ebp-18h] BYREF
  CHAR v16[4]; // [esp+1Ch] [ebp-14h] BYREF
  int *v17; // [esp+20h] [ebp-10h]
  int v18; // [esp+2Ch] [ebp-4h]

  v17 = &v12;
  v13 = a2;
  v4 = *(DispatchDriver **)(a1 + 12);
  v18 = 0;
  DispatchDriver::InvokeHelper(
    v4,
    238,
    wInvokeMethod,
    9u,
    v16,
    dword_1003A63C,
    (unsigned __int16)a3 + 1,
    HIWORD(a3) + 1);
  v6 = ExcelRange::AttachToRange(v5, *(struct IDispatch **)v16);
  DispatchDriver::InvokeHelper(
    v4,
    238,
    wInvokeMethod,
    9u,
    v15,
    dword_1003A63C,
    (unsigned __int16)a4 + 1,
    HIWORD(a4) + 1);
  v8 = ExcelRange::AttachToRange(v7, *(struct IDispatch **)v15);
  DispatchDriver::InvokeHelper(v4, 197, wInvokeMethod, 9u, v14, dword_1003A640, *(_DWORD *)v6, *(_DWORD *)v8);
  v10 = ExcelRange::AttachToRange(v9, *(struct IDispatch **)v14);
  *v13 = v10;
  DispatchDriver::~DispatchDriver(v6);
  operator delete(v6);
  DispatchDriver::~DispatchDriver(v8);
  operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x100203a0  mov     edi, edi
0x100203a2  push    ebp
0x100203a3  mov     ebp, esp
0x100203a5  push    0FFFFFFFFh
0x100203a7  push    offset _XLOLERangeCreate@16_SEH
0x100203ac  mov     eax, large fs:0
0x100203b2  push    eax
0x100203b3  sub     esp, 14h
0x100203b6  push    ebx
0x100203b7  push    esi
0x100203b8  push    edi
0x100203b9  mov     eax, ___security_cookie
0x100203be  xor     eax, ebp
0x100203c0  push    eax
0x100203c1  lea     eax, [ebp+var_C]
0x100203c4  mov     large fs:0, eax
0x100203ca  mov     [ebp+var_10], esp
0x100203cd  mov     [ebp+var_20], edx
0x100203d0  mov     edi, [ecx+0Ch]
0x100203d3  mov     ecx, [ebp+arg_0]
0x100203d6  mov     eax, ecx
0x100203d8  shr     eax, 10h
0x100203db  inc     eax
0x100203dc  mov     [ebp+var_4], 0
0x100203e3  push    eax
0x100203e4  movzx   eax, cx
0x100203e7  inc     eax
0x100203e8  push    eax
0x100203e9  push    offset dword_1003A63C; lpString
0x100203ee  lea     eax, [ebp+var_14]
0x100203f1  push    eax; LPSTR
0x100203f2  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x100203f9  push    9; unsigned __int16
0x100203fb  push    eax; unsigned __int16
0x100203fc  push    0EEh; int
0x10020401  push    edi; this
0x10020402  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x10020407  add     esp, 20h
0x1002040a  push    dword ptr [ebp+var_14]; struct IDispatch *
0x1002040d  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020412  movzx   ecx, [ebp+arg_6]
0x10020416  mov     ebx, eax
0x10020418  inc     ecx
0x10020419  lea     eax, [ebp+var_18]
0x1002041c  push    ecx
0x1002041d  movzx   ecx, [ebp+arg_4]
0x10020421  inc     ecx
0x10020422  push    ecx
0x10020423  push    offset dword_1003A63C; lpString
0x10020428  push    eax; LPSTR
0x10020429  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x10020430  push    9; unsigned __int16
0x10020432  push    eax; unsigned __int16
0x10020433  push    0EEh; int
0x10020438  push    edi; this
0x10020439  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1002043e  add     esp, 20h
0x10020441  push    dword ptr [ebp+var_18]; struct IDispatch *
0x10020444  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020449  mov     esi, eax
0x1002044b  lea     eax, [ebp+var_1C]
0x1002044e  push    dword ptr [esi]
0x10020450  push    dword ptr [ebx]
0x10020452  push    offset dword_1003A640; lpString
0x10020457  push    eax; LPSTR
0x10020458  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x1002045f  push    9; unsigned __int16
0x10020461  push    eax; unsigned __int16
0x10020462  push    0C5h; int
0x10020467  push    edi; this
0x10020468  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1002046d  add     esp, 20h
0x10020470  push    dword ptr [ebp+var_1C]; struct IDispatch *
0x10020473  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020478  mov     ecx, [ebp+var_20]
0x1002047b  mov     [ecx], eax
0x1002047d  mov     ecx, ebx; this
0x1002047f  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10020484  push    8; unsigned int
0x10020486  push    ebx; void *
0x10020487  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002048c  add     esp, 8
0x1002048f  mov     ecx, esi; this
0x10020491  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10020496  push    8; unsigned int
0x10020498  push    esi; void *
0x10020499  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002049e  add     esp, 8
0x100204a1  xor     eax, eax
0x100204a3  mov     ecx, [ebp+var_C]
0x100204a6  mov     large fs:0, ecx
0x100204ad  pop     ecx
0x100204ae  pop     edi
0x100204af  pop     esi
0x100204b0  pop     ebx
0x100204b1  mov     esp, ebp
0x100204b3  pop     ebp
0x100204b4  retn    8
0x100204b7  mov     eax, offset loc_100204BD
0x100204bc  retn
0x100204bd  mov     eax, 0FFFFFFE1h
0x100204c2  mov     ecx, [ebp+var_C]
0x100204c5  mov     large fs:0, ecx
0x100204cc  pop     ecx
0x100204cd  pop     edi
0x100204ce  pop     esi
0x100204cf  pop     ebx
0x100204d0  mov     esp, ebp
0x100204d2  pop     ebp
0x100204d3  retn    8
0x10036880  nop
0x10036881  nop
0x10036882  mov     edx, dword ptr [esp-4+arg_4]
0x10036886  lea     eax, [edx+0Ch]
0x10036889  mov     ecx, [edx-24h]
0x1003688c  xor     ecx, eax; StackCookie
0x1003688e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036893  mov     eax, offset stru_10036FE8
0x10036898  jmp     ___CxxFrameHandler3
```
