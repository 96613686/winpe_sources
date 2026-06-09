# CDSLObject::SelectConnectPageForActiveProvider(HWND__ *,int)

- ea: `0x18004d2a4`
- end: `0x18004d3f2`
- name: `?SelectConnectPageForActiveProvider@CDSLObject@@QEAAXPEAUHWND__@@H@Z`
- size: `334`
- prototype: `void __fastcall(CDSLObject *__hidden this, HWND hWnd, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18004d3f8`

## callees

- `0x180013870`
- `0x18004d2a4`
- `0x180055d3c`

## import_xrefs

- `USER32!SendMessageW` at `0x18004d33c`
- `USER32!SendMessageW` at `0x18004d3d5`
- `USER32!SendMessageW` at `0x18004d33c`
- `USER32!SendMessageW` at `0x18004d3d5`
- `ole32!CoTaskMemAlloc` at `0x18004d37a`
- `ole32!CoTaskMemAlloc` at `0x18004d37a`
- `ole32!CoTaskMemFree` at `0x18004d362`
- `ole32!CoTaskMemFree` at `0x18004d362`

## pseudocode

```c
void __fastcall CDSLObject::SelectConnectPageForActiveProvider(CDSLObject *this, HWND hWnd, int a3)
{
  int v3; // edi
  int PropertyPages; // eax
  unsigned int v8; // ecx
  int i; // edi
  __int64 *v10; // rcx
  __int64 v11; // rdi
  _QWORD *v12; // rax
  int v13; // edi
  struct _PSP **v14; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+18h] BYREF

  v3 = *((_DWORD *)this + 30);
  *((_DWORD *)this + 30) = a3;
  v14 = 0;
  v15 = 0;
  PropertyPages = CDSLProviderInformation::GetPropertyPages(
                    (LPVOID *)(*((_QWORD *)this + 14) + 104LL * a3),
                    this,
                    &v14,
                    &v15);
  if ( PropertyPages >= 0 )
  {
    v8 = *((_DWORD *)this + 66);
    *((_DWORD *)this + 30) = v3;
    for ( i = 1; i < v8; ++i )
    {
      SendMessageW(hWnd, 0x466u, 0, *(_QWORD *)(*((_QWORD *)this + 32) + 8LL * i));
      v8 = *((_DWORD *)this + 66);
    }
    if ( v8 != v15 + 1 )
    {
      v10 = (__int64 *)*((_QWORD *)this + 32);
      v11 = *v10;
      CoTaskMemFree(v10);
      if ( v15 > 0x1FFFFFFE )
        return;
      v12 = CoTaskMemAlloc(8LL * (v15 + 1));
      *((_QWORD *)this + 32) = v12;
      if ( !v12 )
        return;
      *v12 = v11;
      v8 = v15 + 1;
      *((_DWORD *)this + 66) = v15 + 1;
    }
    v13 = 1;
    *((_DWORD *)this + 30) = a3;
    if ( v8 > 1 )
    {
      do
      {
        *(_QWORD *)(*((_QWORD *)this + 32) + 8LL * v13) = v14[v13 - 1];
        SendMessageW(hWnd, 0x467u, 0, *(_QWORD *)(*((_QWORD *)this + 32) + 8LL * v13++));
      }
      while ( (unsigned int)v13 < *((_DWORD *)this + 66) );
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(PropertyPages, L"<CDSLObject::SelectConnectPageForActiveProvider|OLEDB|ERR> ", 0x60Du);
    *((_DWORD *)this + 30) = v3;
  }
}

```

## disassembly

```asm
0x18004d2a4  mov     rax, rsp
0x18004d2a7  mov     [rax+10h], rbx
0x18004d2ab  push    rbp
0x18004d2ac  push    rsi
0x18004d2ad  push    rdi
0x18004d2ae  sub     rsp, 20h
0x18004d2b2  mov     edi, [rcx+78h]
0x18004d2b5  lea     r9, [rax+18h]; unsigned int *
0x18004d2b9  movsxd  rsi, r8d
0x18004d2bc  mov     rbx, rcx
0x18004d2bf  mov     [rcx+78h], esi
0x18004d2c2  lea     r8, [rax+8]; struct _PSP ***
0x18004d2c6  mov     rbp, rdx
0x18004d2c9  mov     qword ptr [rax+8], 0
0x18004d2d1  imul    rcx, rsi, 68h ; 'h'
0x18004d2d5  mov     rdx, rbx; struct CDSLObject *
0x18004d2d8  mov     dword ptr [rax+18h], 0
0x18004d2df  add     rcx, [rbx+70h]; this
0x18004d2e3  call    ?GetPropertyPages@CDSLProviderInformation@@QEAAJPEAVCDSLObject@@PEAPEAPEAU_PSP@@PEAK@Z; CDSLProviderInformation::GetPropertyPages(CDSLObject *,_PSP * * *,ulong *)
0x18004d2e8  test    eax, eax
0x18004d2ea  jns     short loc_18004D311
0x18004d2ec  test    byte ptr cs:_bidGblFlags, 2
0x18004d2f3  jz      short loc_18004D309
0x18004d2f5  mov     r8d, 60Dh; unsigned int
0x18004d2fb  lea     rdx, aCdslobjectSele; "<CDSLObject::SelectConnectPageForActive"...
0x18004d302  mov     ecx, eax; int
0x18004d304  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004d309  mov     [rbx+78h], edi
0x18004d30c  jmp     loc_18004D3E5
0x18004d311  mov     ecx, [rbx+108h]
0x18004d317  mov     [rbx+78h], edi
0x18004d31a  mov     edi, 1
0x18004d31f  cmp     ecx, edi
0x18004d321  jbe     short loc_18004D34E
0x18004d323  mov     r9, [rbx+100h]
0x18004d32a  xor     r8d, r8d; wParam
0x18004d32d  movsxd  rax, edi
0x18004d330  mov     edx, 466h; Msg
0x18004d335  mov     rcx, rbp; hWnd
0x18004d338  mov     r9, [r9+rax*8]; lParam
0x18004d33c  call    cs:__imp_SendMessageW
0x18004d342  mov     ecx, [rbx+108h]
0x18004d348  inc     edi
0x18004d34a  cmp     edi, ecx
0x18004d34c  jb      short loc_18004D323
0x18004d34e  mov     eax, [rsp+38h+arg_10]
0x18004d352  inc     eax
0x18004d354  cmp     ecx, eax
0x18004d356  jz      short loc_18004D39B
0x18004d358  mov     rcx, [rbx+100h]; pv
0x18004d35f  mov     rdi, [rcx]
0x18004d362  call    cs:__imp_CoTaskMemFree
0x18004d368  mov     eax, [rsp+38h+arg_10]
0x18004d36c  cmp     eax, 1FFFFFFEh
0x18004d371  ja      short loc_18004D3E5
0x18004d373  lea     ecx, [rax+1]
0x18004d376  shl     rcx, 3; cb
0x18004d37a  call    cs:__imp_CoTaskMemAlloc
0x18004d380  mov     [rbx+100h], rax
0x18004d387  test    rax, rax
0x18004d38a  jz      short loc_18004D3E5
0x18004d38c  mov     [rax], rdi
0x18004d38f  mov     ecx, [rsp+38h+arg_10]
0x18004d393  inc     ecx
0x18004d395  mov     [rbx+108h], ecx
0x18004d39b  mov     edi, 1
0x18004d3a0  mov     [rbx+78h], esi
0x18004d3a3  cmp     ecx, edi
0x18004d3a5  jbe     short loc_18004D3E5
0x18004d3a7  mov     rax, [rsp+38h+arg_0]
0x18004d3ac  mov     rdx, [rbx+100h]
0x18004d3b3  movsxd  r8, edi
0x18004d3b6  mov     rcx, [rax+r8*8-8]
0x18004d3bb  mov     [rdx+r8*8], rcx
0x18004d3bf  mov     edx, 467h; Msg
0x18004d3c4  mov     r9, [rbx+100h]
0x18004d3cb  mov     rcx, rbp; hWnd
0x18004d3ce  mov     r9, [r9+r8*8]; lParam
0x18004d3d2  xor     r8d, r8d; wParam
0x18004d3d5  call    cs:__imp_SendMessageW
0x18004d3db  inc     edi
0x18004d3dd  cmp     edi, [rbx+108h]
0x18004d3e3  jb      short loc_18004D3A7
0x18004d3e5  mov     rbx, [rsp+38h+arg_8]
0x18004d3ea  add     rsp, 20h
0x18004d3ee  pop     rdi
0x18004d3ef  pop     rsi
0x18004d3f0  pop     rbp
0x18004d3f1  retn
```
