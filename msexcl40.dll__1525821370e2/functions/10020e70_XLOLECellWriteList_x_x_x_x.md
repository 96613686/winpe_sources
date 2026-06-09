# XLOLECellWriteList(x,x,x,x)

- ea: `0x10020e70`
- end: `0x100210f9`
- name: `_XLOLECellWriteList@16`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x1001c090`

## callees

- `0x10006400`
- `0x10018b80`
- `0x1001f730`
- `0x10020750`
- `0x10020e70`
- `0x10021260`
- `0x10021330`
- `0x10021390`
- `0x10021fe0`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x100358c5`
- `0x10035e9f`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x1002103f`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1002103f`
- `OLEAUT32!__imp__VariantInit@4` at `0x10020f07`
- `OLEAUT32!__imp__VariantInit@4` at `0x10020f07`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x100210cf`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x100210cf`
- `OLEAUT32!__imp__VarCyFromR8@12` at `0x10020f67`
- `OLEAUT32!__imp__VarCyFromR8@12` at `0x10020f67`

## pseudocode

```c
int __fastcall XLOLECellWriteList(int a1, DispatchDriver *a2, unsigned __int16 a3, int *a4)
{
  ExcelRange *v5; // ecx
  ExcelNames *v6; // ebx
  __int16 v7; // cx
  int v8; // eax
  WCHAR *v9; // eax
  WCHAR *v10; // ecx
  WCHAR *v11; // edx
  OLECHAR *v13; // eax
  int v15; // ebx
  int v16; // [esp+Ch] [ebp-50h] BYREF
  VARIANTARG pvarg; // [esp+1Ch] [ebp-40h] BYREF
  DispatchDriver *v18; // [esp+2Ch] [ebp-30h]
  int v19; // [esp+30h] [ebp-2Ch]
  CHAR v20[4]; // [esp+34h] [ebp-28h] BYREF
  int v21; // [esp+38h] [ebp-24h]
  WCHAR *v22; // [esp+3Ch] [ebp-20h]
  ExcelNames *v23; // [esp+40h] [ebp-1Ch]
  OLECHAR *psz; // [esp+44h] [ebp-18h]
  unsigned int v25; // [esp+48h] [ebp-14h]
  int *v26; // [esp+4Ch] [ebp-10h]
  int v27; // [esp+58h] [ebp-4h]

  v26 = &v16;
  v18 = a2;
  v21 = a1;
  v19 = *(_DWORD *)(a1 + 804);
  while ( 1 )
  {
    v23 = 0;
    if ( !a4 )
      break;
    v27 = 0;
    DispatchDriver::InvokeHelper(
      a2,
      238,
      wInvokeMethod,
      9u,
      v20,
      dword_1003A628,
      a3 + 1,
      *((unsigned __int8 *)a4 + 4) + 1);
    v6 = ExcelRange::AttachToRange(v5, *(struct IDispatch **)v20);
    v23 = v6;
    VariantInit(&pvarg);
    v7 = *((_WORD *)a4 + 4);
    if ( (v7 & 0x800) != 0 )
      goto LABEL_23;
    if ( (v7 & 2) != 0 )
    {
      if ( (v7 & 0x40) != 0 )
      {
        pvarg.vt = 7;
        pvarg.llVal = *((_QWORD *)a4 + 3);
      }
      else if ( (v7 & 0x20) != 0 && *(int *)(v19 + 4) > 5 )
      {
        pvarg.vt = 6;
        VarCyFromR8(*((DOUBLE *)a4 + 3), &pvarg.cyVal);
      }
      else
      {
        pvarg.vt = 5;
        pvarg.llVal = *((_QWORD *)a4 + 3);
      }
    }
    else
    {
      if ( (v7 & 4) != 0 )
      {
        pvarg.vt = 11;
        pvarg.iVal = *((_WORD *)a4 + 12);
        goto LABEL_24;
      }
      if ( (v7 & 0x10) == 0 )
      {
LABEL_23:
        pvarg.vt = 0;
        goto LABEL_24;
      }
      v8 = a4[6];
      if ( !v8 || v8 == -1 )
        v9 = &WideCharStr;
      else
        v9 = (WCHAR *)(v8 + 14);
      v10 = v9;
      v22 = v9;
      v11 = v9 + 1;
      while ( *v10++ )
        ;
      v25 = 2 * (v10 - v11) + 4;
      v13 = (OLECHAR *)MemAllocate(v25);
      psz = v13;
      if ( !v13 )
        return -1011;
      v25 >>= 1;
      WCSCPY2(v13, L"'", v25);
      WCSCAT2(psz, v22, v25);
      pvarg.vt = 8;
      pvarg.lVal = (LONG)SysAllocString(psz);
      MemFree(psz);
    }
LABEL_24:
    DispatchDriver::SetProperty(v6, 6, 12, &pvarg);
    if ( v6 )
    {
      DispatchDriver::~DispatchDriver(v6);
      operator delete(v6, 8u);
    }
    a2 = v18;
    v27 = -1;
    a4 = (int *)*a4;
  }
  v15 = v21;
  if ( *(_DWORD *)(v21 + 24) )
  {
    SafeArrayDestroy(*(SAFEARRAY **)(v21 + 24));
    *(_DWORD *)(v15 + 24) = 0;
  }
  *(_DWORD *)(v15 + 16) = -1;
  return 0;
}

```

## disassembly

```asm
0x10020e70  mov     edi, edi
0x10020e72  push    ebp
0x10020e73  mov     ebp, esp
0x10020e75  push    0FFFFFFFFh
0x10020e77  push    offset _XLOLECellWriteList@16_SEH
0x10020e7c  mov     eax, large fs:0
0x10020e82  push    eax
0x10020e83  sub     esp, 34h
0x10020e86  push    ebx
0x10020e87  push    esi
0x10020e88  push    edi
0x10020e89  mov     eax, ___security_cookie
0x10020e8e  xor     eax, ebp
0x10020e90  push    eax
0x10020e91  lea     eax, [ebp+var_C]
0x10020e94  mov     large fs:0, eax
0x10020e9a  mov     [ebp+var_10], esp
0x10020e9d  mov     [ebp+var_30], edx
0x10020ea0  mov     ebx, ecx
0x10020ea2  mov     [ebp+var_24], ebx
0x10020ea5  mov     eax, [ebx+324h]
0x10020eab  mov     edi, [ebp+arg_4]
0x10020eae  mov     esi, [ebp+arg_0]
0x10020eb1  mov     [ebp+var_2C], eax
0x10020eb4  mov     [ebp+var_1C], 0
0x10020ebb  test    edi, edi
0x10020ebd  jz      loc_100210C4
0x10020ec3  mov     [ebp+var_4], 0
0x10020eca  movzx   eax, byte ptr [edi+4]
0x10020ece  inc     eax
0x10020ecf  push    eax
0x10020ed0  movzx   eax, si
0x10020ed3  inc     eax
0x10020ed4  push    eax
0x10020ed5  push    offset dword_1003A628; lpString
0x10020eda  lea     eax, [ebp+var_28]
0x10020edd  push    eax; LPSTR
0x10020ede  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x10020ee5  push    9; unsigned __int16
0x10020ee7  push    eax; unsigned __int16
0x10020ee8  push    0EEh; int
0x10020eed  push    edx; this
0x10020eee  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x10020ef3  add     esp, 20h
0x10020ef6  push    dword ptr [ebp+var_28]; struct IDispatch *
0x10020ef9  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020efe  mov     ebx, eax
0x10020f00  lea     eax, [ebp+pvarg]
0x10020f03  push    eax; pvarg
0x10020f04  mov     [ebp+var_1C], ebx
0x10020f07  call    ds:__imp__VariantInit@4; VariantInit(x)
0x10020f0d  movzx   ecx, word ptr [edi+8]
0x10020f11  test    ecx, 800h
0x10020f17  jnz     loc_10021052
0x10020f1d  test    cl, 2
0x10020f20  jz      short loc_10020F8A
0x10020f22  test    cl, 40h
0x10020f25  jz      short loc_10020F3F
0x10020f27  mov     eax, 7
0x10020f2c  mov     word ptr [ebp+pvarg], ax
0x10020f30  movsd   xmm0, qword ptr [edi+18h]
0x10020f35  movsd   qword ptr [ebp+pvarg+8], xmm0
0x10020f3a  jmp     loc_10021058
0x10020f3f  test    cl, 20h
0x10020f42  jz      short loc_10020F72
0x10020f44  mov     eax, [ebp+var_2C]
0x10020f47  cmp     dword ptr [eax+4], 5
0x10020f4b  jle     short loc_10020F72
0x10020f4d  mov     eax, 6
0x10020f52  mov     word ptr [ebp+pvarg], ax
0x10020f56  lea     eax, [ebp+pvarg+8]
0x10020f59  movsd   xmm0, qword ptr [edi+18h]
0x10020f5e  push    eax; pcyOut
0x10020f5f  sub     esp, 8
0x10020f62  movsd   [esp+5Ch+dblIn], xmm0; dblIn
0x10020f67  call    ds:__imp__VarCyFromR8@12; VarCyFromR8(x,x,x)
0x10020f6d  jmp     loc_10021058
0x10020f72  mov     eax, 5
0x10020f77  mov     word ptr [ebp+pvarg], ax
0x10020f7b  movsd   xmm0, qword ptr [edi+18h]
0x10020f80  movsd   qword ptr [ebp+pvarg+8], xmm0
0x10020f85  jmp     loc_10021058
0x10020f8a  test    cl, 4
0x10020f8d  jz      short loc_10020FA5
0x10020f8f  mov     eax, 0Bh
0x10020f94  mov     word ptr [ebp+pvarg], ax
0x10020f98  mov     ax, [edi+18h]
0x10020f9c  mov     word ptr [ebp+pvarg+8], ax
0x10020fa0  jmp     loc_10021058
0x10020fa5  test    cl, 10h
0x10020fa8  jz      loc_10021052
0x10020fae  mov     eax, [edi+18h]
0x10020fb1  test    eax, eax
0x10020fb3  jz      short loc_10020FBF
0x10020fb5  cmp     eax, 0FFFFFFFFh
0x10020fb8  jz      short loc_10020FBF
0x10020fba  add     eax, 0Eh
0x10020fbd  jmp     short loc_10020FC4
0x10020fbf  mov     eax, offset WideCharStr
0x10020fc4  mov     ecx, eax
0x10020fc6  mov     [ebp+var_20], eax
0x10020fc9  lea     edx, [ecx+2]
0x10020fcc  nop     dword ptr [eax+00h]
0x10020fd0  mov     ax, [ecx]
0x10020fd3  add     ecx, 2
0x10020fd6  test    ax, ax
0x10020fd9  jnz     short loc_10020FD0
0x10020fdb  sub     ecx, edx
0x10020fdd  sar     ecx, 1
0x10020fdf  lea     eax, ds:4[ecx*2]
0x10020fe6  mov     ecx, eax
0x10020fe8  mov     [ebp+var_14], eax
0x10020feb  call    _MemAllocate@4; MemAllocate(x)
0x10020ff0  mov     [ebp+psz], eax
0x10020ff3  test    eax, eax
0x10020ff5  jnz     short loc_10021010
0x10020ff7  mov     eax, 0FFFFFC0Dh
0x10020ffc  mov     ecx, [ebp+var_C]
0x10020fff  mov     large fs:0, ecx
0x10021006  pop     ecx
0x10021007  pop     edi
0x10021008  pop     esi
0x10021009  pop     ebx
0x1002100a  mov     esp, ebp
0x1002100c  pop     ebp
0x1002100d  retn    8
0x10021010  mov     ecx, [ebp+var_14]
0x10021013  mov     edx, offset asc_10005114; "'"
0x10021018  shr     ecx, 1
0x1002101a  mov     [ebp+var_14], ecx
0x1002101d  push    ecx
0x1002101e  mov     ecx, eax
0x10021020  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10021025  push    [ebp+var_14]
0x10021028  mov     edx, [ebp+var_20]
0x1002102b  mov     ecx, [ebp+psz]
0x1002102e  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10021033  push    [ebp+psz]; psz
0x10021036  mov     eax, 8
0x1002103b  mov     word ptr [ebp+pvarg], ax
0x1002103f  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10021045  mov     ecx, [ebp+psz]
0x10021048  mov     dword ptr [ebp+pvarg+8], eax
0x1002104b  call    _MemFree@4; MemFree(x)
0x10021050  jmp     short loc_10021058
0x10021052  xor     eax, eax
0x10021054  mov     word ptr [ebp+pvarg], ax
0x10021058  lea     eax, [ebp+pvarg]
0x1002105b  push    eax
0x1002105c  push    0Ch; char
0x1002105e  push    6; int
0x10021060  push    ebx; this
0x10021061  call    ?SetProperty@DispatchDriver@@QAAHJGZZ; DispatchDriver::SetProperty(long,ushort,...)
0x10021066  add     esp, 10h
0x10021069  test    ebx, ebx
0x1002106b  jz      short loc_1002107F
0x1002106d  mov     ecx, ebx; this
0x1002106f  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10021074  push    8; unsigned int
0x10021076  push    ebx; void *
0x10021077  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002107c  add     esp, 8
0x1002107f  mov     edx, [ebp+var_30]
0x10021082  mov     [ebp+var_4], 0FFFFFFFFh
0x10021089  mov     edi, [edi]
0x1002108b  jmp     loc_10020EB4
0x10021090  mov     ecx, [ebp+var_1C]; this
0x10021093  test    ecx, ecx
0x10021095  jz      short loc_1002109D
0x10021097  push    ecx; unsigned int
0x10021098  call    ??_GExcelNames@@QAEPAXI@Z; ExcelNames::`scalar deleting destructor'(uint)
0x1002109d  mov     ecx, [ebp+var_24]
0x100210a0  call    _XLOLECellClearCache@4; XLOLECellClearCache(x)
0x100210a5  mov     eax, offset loc_100210AB
0x100210aa  retn
0x100210ab  mov     eax, 0FFFFFFE0h
0x100210b0  mov     ecx, [ebp+var_C]
0x100210b3  mov     large fs:0, ecx
0x100210ba  pop     ecx
0x100210bb  pop     edi
0x100210bc  pop     esi
0x100210bd  pop     ebx
0x100210be  mov     esp, ebp
0x100210c0  pop     ebp
0x100210c1  retn    8
0x100210c4  mov     ebx, [ebp+var_24]
0x100210c7  mov     eax, [ebx+18h]
0x100210ca  test    eax, eax
0x100210cc  jz      short loc_100210DC
0x100210ce  push    eax; psa
0x100210cf  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x100210d5  mov     dword ptr [ebx+18h], 0
0x100210dc  mov     dword ptr [ebx+10h], 0FFFFFFFFh
0x100210e3  xor     eax, eax
0x100210e5  mov     ecx, [ebp+var_C]
0x100210e8  mov     large fs:0, ecx
0x100210ef  pop     ecx
0x100210f0  pop     edi
0x100210f1  pop     esi
0x100210f2  pop     ebx
0x100210f3  mov     esp, ebp
0x100210f5  pop     ebp
0x100210f6  retn    8
0x10036970  nop
0x10036971  nop
0x10036972  mov     edx, [esp-4+arg_4]
0x10036976  lea     eax, [edx+0Ch]
0x10036979  mov     ecx, [edx-44h]
0x1003697c  xor     ecx, eax; StackCookie
0x1003697e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036983  mov     eax, offset stru_100371A0
0x10036988  jmp     ___CxxFrameHandler3
```
