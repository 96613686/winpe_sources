# CScriptRuntime::Delete(void)

- ea: `0x18004f578`
- end: `0x18004f748`
- name: `?Delete@CScriptRuntime@@AEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180023440`

## callees

- `0x180005660`
- `0x18000599c`
- `0x180007e9c`
- `0x180011bc4`
- `0x18003477c`
- `0x18004f578`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004f6d6`
- `OLEAUT32!__imp_VariantClear` at `0x18004f6d6`

## pseudocode

```c
int __fastcall CScriptRuntime::Delete(CScriptRuntime *this)
{
  __int64 v1; // r8
  int v2; // ebx
  int v3; // r14d
  int v5; // eax
  __int64 v6; // rsi
  struct CSession *v7; // rcx
  int result; // eax
  const unsigned __int16 *bstrVal; // rdx
  __int64 v10; // r8
  struct SYM *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _WORD *v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  VARIANTARG v17; // [rsp+48h] [rbp-18h] BYREF
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
      result = ConvertToString(v7, (struct IDispatch ***)&pvarg, &v17, 1);
      v2 = result;
      if ( result < 0 )
        return result;
    }
    else
    {
      result = ConvertNumberToString(v7, (struct VAR **)&pvarg);
      v2 = result;
      if ( result < 0 )
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
          return -2147418113;
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
0x18004f578  mov     [rsp-28h+arg_10], rbx
0x18004f57d  push    rbp
0x18004f57e  push    rsi
0x18004f57f  push    rdi
0x18004f580  push    r12
0x18004f582  push    r14
0x18004f584  mov     rbp, rsp
0x18004f587  sub     rsp, 60h
0x18004f58b  mov     r8, [rcx+90h]; struct VAR *
0x18004f592  xor     eax, eax
0x18004f594  xorps   xmm0, xmm0
0x18004f597  mov     [rbp+pvarg], 0
0x18004f59f  mov     [rbp+arg_0], 0
0x18004f5a6  xor     ebx, ebx
0x18004f5a8  movups  [rbp+var_30], xmm0
0x18004f5ac  mov     [rbp+var_20], rax
0x18004f5b0  lea     r12d, [rax+1]
0x18004f5b4  movzx   edx, word ptr [r8]
0x18004f5b8  xor     r14d, r14d
0x18004f5bb  mov     rdi, rcx
0x18004f5be  sub     edx, 83h
0x18004f5c4  jz      loc_18004F6E4
0x18004f5ca  sub     edx, r12d
0x18004f5cd  jz      short loc_18004F645
0x18004f5cf  cmp     edx, r12d
0x18004f5d2  jz      short loc_18004F5ED
0x18004f5d4  mov     rcx, [rcx]; this
0x18004f5d7  xor     r9d, r9d; Src
0x18004f5da  mov     edx, 800A1394h; int
0x18004f5df  mov     [rsp+60h+var_40], eax; int
0x18004f5e3  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18004f5e8  jmp     loc_18004F714
0x18004f5ed  mov     rax, [r8+10h]
0x18004f5f1  lea     rdx, [rbp+pvarg]; struct VAR **
0x18004f5f5  mov     rsi, [r8+8]
0x18004f5f9  mov     [rbp+pvarg], rax
0x18004f5fd  movzx   ecx, word ptr [rax]
0x18004f600  mov     eax, 0FFFDh
0x18004f605  sub     cx, 3
0x18004f609  test    ax, cx
0x18004f60c  mov     rcx, [rdi]; struct CSession *
0x18004f60f  jz      short loc_18004F629
0x18004f611  mov     r9d, r12d; int
0x18004f614  lea     r8, [rbp+var_18]; struct VAR *
0x18004f618  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18004f61d  mov     ebx, eax
0x18004f61f  test    eax, eax
0x18004f621  js      loc_18004F733
0x18004f627  jmp     short loc_18004F63B
0x18004f629  call    ?ConvertNumberToString@@YAJPEAVCSession@@PEAPEAVVAR@@@Z; ConvertNumberToString(CSession *,VAR * *)
0x18004f62e  mov     ebx, eax
0x18004f630  test    eax, eax
0x18004f632  js      loc_18004F733
0x18004f638  mov     r14d, r12d
0x18004f63b  mov     rax, [rbp+pvarg]
0x18004f63f  mov     rdx, [rax+8]
0x18004f643  jmp     short loc_18004F656
0x18004f645  mov     rsi, [r8+8]
0x18004f649  test    rsi, rsi
0x18004f64c  jz      loc_18004F716
0x18004f652  mov     rdx, [r8+10h]; unsigned __int16 *
0x18004f656  movzx   ecx, word ptr [rsi]
0x18004f659  sub     ecx, 9
0x18004f65c  jz      short loc_18004F6AA
0x18004f65e  sub     ecx, 78h ; 'x'
0x18004f661  jz      short loc_18004F672
0x18004f663  sub     ecx, 5
0x18004f666  jz      short loc_18004F6AA
0x18004f668  sub     ecx, r12d
0x18004f66b  jz      short loc_18004F672
0x18004f66d  cmp     ecx, 9
0x18004f670  jnz     short loc_18004F6CD
0x18004f672  mov     rax, [rdi]
0x18004f675  mov     r8, [rax+28h]
0x18004f679  test    r8, r8
0x18004f67c  jnz     short loc_18004F688
0x18004f67e  mov     eax, 8000FFFFh
0x18004f683  jmp     loc_18004F733
0x18004f688  mov     r8d, [r8+3F0h]
0x18004f68f  mov     rcx, [rsi+8]
0x18004f693  shl     r8d, 1Ch
0x18004f697  or      r8d, r12d
0x18004f69a  mov     rax, [rcx]
0x18004f69d  mov     rax, [rax+48h]
0x18004f6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6a6  mov     ebx, eax
0x18004f6a8  jmp     short loc_18004F6CD
0x18004f6aa  lea     rcx, [rbp+var_30]; this
0x18004f6ae  call    ?InitFromBstr@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromBstr(ushort const *)
0x18004f6b3  mov     rdx, [rsi+8]; struct IDispatch *
0x18004f6b7  lea     r9, [rbp+arg_0]; int *
0x18004f6bb  mov     rcx, [rdi]; struct CSession *
0x18004f6be  mov     r8, rax; struct SYM *
0x18004f6c1  call    ?GetDispatchDispID@@YAJPEAVCSession@@PEAUIDispatch@@PEAUSYM@@PEAJ@Z; GetDispatchDispID(CSession *,IDispatch *,SYM *,long *)
0x18004f6c6  xor     ebx, ebx
0x18004f6c8  test    eax, eax
0x18004f6ca  setns   bl
0x18004f6cd  test    r14d, r14d
0x18004f6d0  jz      short loc_18004F716
0x18004f6d2  mov     rcx, [rbp+pvarg]; pvarg
0x18004f6d6  call    cs:__imp_VariantClear
0x18004f6dd  nop     dword ptr [rax+rax+00h]
0x18004f6e2  jmp     short loc_18004F716
0x18004f6e4  mov     rdx, [r8+8]
0x18004f6e8  movzx   ecx, word ptr [rdx]
0x18004f6eb  sub     ecx, 81h
0x18004f6f1  jz      short loc_18004F6FD
0x18004f6f3  sub     ecx, 6
0x18004f6f6  jz      short loc_18004F6FD
0x18004f6f8  cmp     ecx, 9
0x18004f6fb  jnz     short loc_18004F716
0x18004f6fd  mov     rcx, [rdx+8]
0x18004f701  mov     edx, [r8+4]
0x18004f705  mov     [rbp+arg_0], edx
0x18004f708  mov     rax, [rcx]
0x18004f70b  mov     rax, [rax+50h]
0x18004f70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f714  mov     ebx, eax
0x18004f716  mov     rcx, [rdi+90h]
0x18004f71d  xor     eax, eax
0x18004f71f  test    ebx, ebx
0x18004f721  setnz   al
0x18004f724  sub     ax, r12w
0x18004f728  mov     word ptr [rcx], 0Bh
0x18004f72d  mov     [rcx+8], ax
0x18004f731  mov     eax, ebx
0x18004f733  mov     rbx, [rsp+60h+arg_10]
0x18004f73b  add     rsp, 60h
0x18004f73f  pop     r14
0x18004f741  pop     r12
0x18004f743  pop     rdi
0x18004f744  pop     rsi
0x18004f745  pop     rbp
0x18004f746  retn
```
