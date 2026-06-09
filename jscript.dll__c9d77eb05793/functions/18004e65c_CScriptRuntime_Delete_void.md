# CScriptRuntime::Delete(void)

- ea: `0x18004e65c`
- end: `0x18004e825`
- name: `?Delete@CScriptRuntime@@AEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180026230`

## callees

- `0x180006bf0`
- `0x180006ed8`
- `0x18000ad6c`
- `0x180014dc0`
- `0x180016714`
- `0x18004e65c`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004e7ba`
- `OLEAUT32!__imp_VariantClear` at `0x18004e7ba`

## pseudocode

```c
__int64 __fastcall CScriptRuntime::Delete(CScriptRuntime *this)
{
  __int64 v1; // r8
  unsigned int v2; // ebx
  int v3; // r14d
  unsigned int v5; // eax
  __int64 v6; // rsi
  struct CSession *v7; // rcx
  __int64 result; // rax
  const unsigned __int16 *bstrVal; // rdx
  __int64 v10; // r8
  struct SYM *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _WORD *v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  _BYTE v17[24]; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+90h] [rbp+30h] BYREF
  VARIANTARG *pvarg; // [rsp+98h] [rbp+38h] BYREF

  v1 = *((_QWORD *)this + 18);
  pvarg = 0;
  v18 = 0;
  v2 = 0;
  v15 = 0;
  v16 = 0;
  v3 = 0;
  if ( *(_WORD *)v1 == 131 )
  {
    v12 = *(_QWORD *)(v1 + 8);
    if ( *(_WORD *)v12 != 129 && *(_WORD *)v12 != 135 && *(_WORD *)v12 != 144 )
      goto LABEL_29;
    v13 = *(_QWORD *)(v12 + 8);
    v18 = *(_DWORD *)(v1 + 4);
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
    goto LABEL_28;
  }
  if ( *(_WORD *)v1 != 132 )
  {
    if ( *(_WORD *)v1 != 133 )
    {
      v5 = CSession::RecordHr(*(CSession **)this, -2146823276, (struct VAR *)v1, 0, 0);
LABEL_28:
      v2 = v5;
      goto LABEL_29;
    }
    v6 = *(_QWORD *)(v1 + 8);
    pvarg = *(VARIANTARG **)(v1 + 16);
    v7 = *(struct CSession **)this;
    if ( ((pvarg->vt - 3) & 0xFFFD) != 0 )
    {
      result = ConvertToString(v7, (struct VAR **)&pvarg, (struct VAR *)v17, 1);
      v2 = result;
      if ( (int)result < 0 )
        return result;
    }
    else
    {
      result = ConvertNumberToString(v7, (struct VAR **)&pvarg);
      v2 = result;
      if ( (int)result < 0 )
        return result;
      v3 = 1;
    }
    bstrVal = pvarg->bstrVal;
    goto LABEL_13;
  }
  v6 = *(_QWORD *)(v1 + 8);
  if ( v6 )
  {
    bstrVal = *(const unsigned __int16 **)(v1 + 16);
LABEL_13:
    switch ( *(_WORD *)v6 )
    {
      case 9:
        goto LABEL_21;
      case 0x81:
LABEL_18:
        v10 = *(_QWORD *)(*(_QWORD *)this + 40LL);
        if ( !v10 )
          return 2147549183LL;
        v2 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**(_QWORD **)(v6 + 8) + 72LL))(
               *(_QWORD *)(v6 + 8),
               bstrVal,
               (*(_DWORD *)(v10 + 1008) << 28) | 1u);
        break;
      case 0x86:
LABEL_21:
        v11 = SYM::InitFromBstr((SYM *)&v15, bstrVal);
        v2 = GetDispatchDispID(*(struct CSession **)this, *(struct IDispatch **)(v6 + 8), v11, &v18) >= 0;
        break;
      case 0x87:
      case 0x90:
        goto LABEL_18;
    }
    if ( v3 )
      VariantClear(pvarg);
  }
LABEL_29:
  v14 = (_WORD *)*((_QWORD *)this + 18);
  *v14 = 11;
  v14[4] = (v2 != 0) - 1;
  return v2;
}

```

## disassembly

```asm
0x18004e65c  mov     [rsp-28h+arg_10], rbx
0x18004e661  push    rbp
0x18004e662  push    rsi
0x18004e663  push    rdi
0x18004e664  push    r12
0x18004e666  push    r14
0x18004e668  mov     rbp, rsp
0x18004e66b  sub     rsp, 60h
0x18004e66f  mov     r8, [rcx+90h]; struct VAR *
0x18004e676  xor     eax, eax
0x18004e678  xorps   xmm0, xmm0
0x18004e67b  mov     [rbp+pvarg], 0
0x18004e683  mov     [rbp+arg_0], 0
0x18004e68a  xor     ebx, ebx
0x18004e68c  movups  [rbp+var_30], xmm0
0x18004e690  mov     [rbp+var_20], rax
0x18004e694  lea     r12d, [rax+1]
0x18004e698  movzx   edx, word ptr [r8]
0x18004e69c  xor     r14d, r14d
0x18004e69f  mov     rdi, rcx
0x18004e6a2  sub     edx, 83h
0x18004e6a8  jz      loc_18004E7C2
0x18004e6ae  sub     edx, r12d
0x18004e6b1  jz      short loc_18004E729
0x18004e6b3  cmp     edx, r12d
0x18004e6b6  jz      short loc_18004E6D1
0x18004e6b8  mov     rcx, [rcx]; this
0x18004e6bb  xor     r9d, r9d; Src
0x18004e6be  mov     edx, 800A1394h; int
0x18004e6c3  mov     [rsp+60h+var_40], eax; int
0x18004e6c7  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18004e6cc  jmp     loc_18004E7F2
0x18004e6d1  mov     rax, [r8+10h]
0x18004e6d5  lea     rdx, [rbp+pvarg]; struct VAR **
0x18004e6d9  mov     rsi, [r8+8]
0x18004e6dd  mov     [rbp+pvarg], rax
0x18004e6e1  movzx   ecx, word ptr [rax]
0x18004e6e4  mov     eax, 0FFFDh
0x18004e6e9  sub     cx, 3
0x18004e6ed  test    ax, cx
0x18004e6f0  mov     rcx, [rdi]; this
0x18004e6f3  jz      short loc_18004E70D
0x18004e6f5  mov     r9d, r12d; int
0x18004e6f8  lea     r8, [rbp+var_18]; struct VAR *
0x18004e6fc  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18004e701  mov     ebx, eax
0x18004e703  test    eax, eax
0x18004e705  js      loc_18004E811
0x18004e70b  jmp     short loc_18004E71F
0x18004e70d  call    ?ConvertNumberToString@@YAJPEAVCSession@@PEAPEAVVAR@@@Z; ConvertNumberToString(CSession *,VAR * *)
0x18004e712  mov     ebx, eax
0x18004e714  test    eax, eax
0x18004e716  js      loc_18004E811
0x18004e71c  mov     r14d, r12d
0x18004e71f  mov     rax, [rbp+pvarg]
0x18004e723  mov     rdx, [rax+8]
0x18004e727  jmp     short loc_18004E73A
0x18004e729  mov     rsi, [r8+8]
0x18004e72d  test    rsi, rsi
0x18004e730  jz      loc_18004E7F4
0x18004e736  mov     rdx, [r8+10h]; unsigned __int16 *
0x18004e73a  movzx   ecx, word ptr [rsi]
0x18004e73d  sub     ecx, 9
0x18004e740  jz      short loc_18004E78E
0x18004e742  sub     ecx, 78h ; 'x'
0x18004e745  jz      short loc_18004E756
0x18004e747  sub     ecx, 5
0x18004e74a  jz      short loc_18004E78E
0x18004e74c  sub     ecx, r12d
0x18004e74f  jz      short loc_18004E756
0x18004e751  cmp     ecx, 9
0x18004e754  jnz     short loc_18004E7B1
0x18004e756  mov     rax, [rdi]
0x18004e759  mov     r8, [rax+28h]
0x18004e75d  test    r8, r8
0x18004e760  jnz     short loc_18004E76C
0x18004e762  mov     eax, 8000FFFFh
0x18004e767  jmp     loc_18004E811
0x18004e76c  mov     r8d, [r8+3F0h]
0x18004e773  mov     rcx, [rsi+8]
0x18004e777  shl     r8d, 1Ch
0x18004e77b  or      r8d, r12d
0x18004e77e  mov     rax, [rcx]
0x18004e781  mov     rax, [rax+48h]
0x18004e785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e78a  mov     ebx, eax
0x18004e78c  jmp     short loc_18004E7B1
0x18004e78e  lea     rcx, [rbp+var_30]; this
0x18004e792  call    ?InitFromBstr@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromBstr(ushort const *)
0x18004e797  mov     rdx, [rsi+8]; struct IDispatch *
0x18004e79b  lea     r9, [rbp+arg_0]; int *
0x18004e79f  mov     rcx, [rdi]; struct CSession *
0x18004e7a2  mov     r8, rax; struct SYM *
0x18004e7a5  call    ?GetDispatchDispID@@YAJPEAVCSession@@PEAUIDispatch@@PEAUSYM@@PEAJ@Z; GetDispatchDispID(CSession *,IDispatch *,SYM *,long *)
0x18004e7aa  xor     ebx, ebx
0x18004e7ac  test    eax, eax
0x18004e7ae  setns   bl
0x18004e7b1  test    r14d, r14d
0x18004e7b4  jz      short loc_18004E7F4
0x18004e7b6  mov     rcx, [rbp+pvarg]; pvarg
0x18004e7ba  call    cs:__imp_VariantClear
0x18004e7c0  jmp     short loc_18004E7F4
0x18004e7c2  mov     rdx, [r8+8]
0x18004e7c6  movzx   ecx, word ptr [rdx]
0x18004e7c9  sub     ecx, 81h
0x18004e7cf  jz      short loc_18004E7DB
0x18004e7d1  sub     ecx, 6
0x18004e7d4  jz      short loc_18004E7DB
0x18004e7d6  cmp     ecx, 9
0x18004e7d9  jnz     short loc_18004E7F4
0x18004e7db  mov     rcx, [rdx+8]
0x18004e7df  mov     edx, [r8+4]
0x18004e7e3  mov     [rbp+arg_0], edx
0x18004e7e6  mov     rax, [rcx]
0x18004e7e9  mov     rax, [rax+50h]
0x18004e7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7f2  mov     ebx, eax
0x18004e7f4  mov     rcx, [rdi+90h]
0x18004e7fb  xor     eax, eax
0x18004e7fd  test    ebx, ebx
0x18004e7ff  setnz   al
0x18004e802  sub     ax, r12w
0x18004e806  mov     word ptr [rcx], 0Bh
0x18004e80b  mov     [rcx+8], ax
0x18004e80f  mov     eax, ebx
0x18004e811  mov     rbx, [rsp+60h+arg_10]
0x18004e819  add     rsp, 60h
0x18004e81d  pop     r14
0x18004e81f  pop     r12
0x18004e821  pop     rdi
0x18004e822  pop     rsi
0x18004e823  pop     rbp
0x18004e824  retn
```
