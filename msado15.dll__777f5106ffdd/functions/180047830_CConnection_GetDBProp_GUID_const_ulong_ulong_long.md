# CConnection::GetDBProp(_GUID const &,ulong,ulong *,long *)

- ea: `0x180047830`
- end: `0x1800479f6`
- name: `?GetDBProp@CConnection@@UEAAJAEBU_GUID@@KPEAKPEAJ@Z`
- size: `454`
- prototype: `__int64 __fastcall(CConnection *__hidden this, const struct _GUID *, unsigned int, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180047830`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004791b`
- `ole32!CoTaskMemFree` at `0x18004792a`
- `ole32!CoTaskMemFree` at `0x18004791b`
- `ole32!CoTaskMemFree` at `0x18004792a`
- `OLEAUT32!__imp_VariantClear` at `0x180047905`
- `OLEAUT32!__imp_VariantClear` at `0x180047905`

## pseudocode

```c
__int64 __fastcall CConnection::GetDBProp(CConnection *this, const struct _GUID *a2, int a3, unsigned int *a4, int *a5)
{
  __int128 v5; // xmm0
  __int64 v7; // rcx
  unsigned int v9; // edi
  _DWORD *v10; // rbx
  unsigned int v11; // esi
  unsigned int BidObjectID; // eax
  __int64 v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+30h] [rbp-68h] BYREF
  int v16; // [rsp+38h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-58h] BYREF
  int *v18; // [rsp+48h] [rbp-50h] BYREF
  int v19; // [rsp+50h] [rbp-48h]
  __int128 v20; // [rsp+54h] [rbp-44h]
  int v21; // [rsp+64h] [rbp-34h]

  v5 = (__int128)*a2;
  v16 = a3;
  v21 = 0;
  v19 = 1;
  v7 = *((_QWORD *)this + 123);
  v18 = &v16;
  pv = 0;
  v15 = 0;
  v20 = v5;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, int **, int *, LPVOID *))(*(_QWORD *)v7 + 24LL))(
         v7,
         1,
         &v18,
         &v15,
         &pv);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147217887 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
      {
        bidTraceW(off_18012A1C0[0], 5246985, L"<CConnection::GetDBProp|ADO|ERR>  line %d\n", 5124);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(v14) = 5124;
        bidTraceW(off_18012A1C0[0], 5246985, L"<CConnection::GetDBProp|ADO|ERR> %u#, line %d\n", BidObjectID, v14);
      }
    }
    return v9;
  }
  if ( v15 )
  {
    v10 = pv;
    if ( v9 == -2147217887 )
    {
      if ( a4 && *(_QWORD *)pv )
        *a4 = *(_DWORD *)(*(_QWORD *)pv + 8LL);
    }
    else if ( *(_WORD *)(*(_QWORD *)pv + 48LL) )
    {
      *a5 = *(_DWORD *)(*(_QWORD *)pv + 56LL);
    }
    else
    {
      *a5 = 0;
    }
    if ( v10[2] )
    {
      v11 = 0;
      do
        VariantClear((VARIANTARG *)(*(_QWORD *)v10 + 8 * (9LL * v11++ + 6)));
      while ( v11 < v10[2] );
      CoTaskMemFree(*(LPVOID *)v10);
    }
    CoTaskMemFree(v10);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x180047830  mov     r11, rsp
0x180047833  push    rbx
0x180047834  push    rbp
0x180047835  push    rsi
0x180047836  push    rdi
0x180047837  push    r14
0x180047839  sub     rsp, 70h
0x18004783d  mov     rax, cs:__security_cookie
0x180047844  xor     rax, rsp
0x180047847  mov     [rsp+98h+var_30], rax
0x18004784c  movups  xmm0, xmmword ptr [rdx]
0x18004784f  mov     rsi, [rsp+98h+arg_20]
0x180047857  lea     rax, [r11-60h]
0x18004785b  mov     [r11-60h], r8d
0x18004785f  xor     ebp, ebp
0x180047861  mov     [rsp+98h+var_34], ebp
0x180047865  lea     r8, [r11-58h]
0x180047869  mov     [rsp+98h+var_48], 1
0x180047871  mov     rbx, rcx
0x180047874  mov     rcx, [rcx+3D8h]
0x18004787b  mov     r14, r9
0x18004787e  mov     [r11-50h], rax
0x180047882  lea     r9, [r11-68h]
0x180047886  mov     [r11-58h], rbp
0x18004788a  mov     edx, 1
0x18004788f  mov     [rsp+98h+var_68], ebp
0x180047893  movups  [rsp+98h+var_44], xmm0
0x180047898  mov     rax, [rcx]
0x18004789b  mov     [r11-78h], r8
0x18004789f  lea     r8, [r11-50h]
0x1800478a3  mov     rax, [rax+18h]
0x1800478a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478ac  mov     edi, eax
0x1800478ae  mov     eax, 80000000h
0x1800478b3  lea     ecx, [rdi+rax]
0x1800478b6  test    eax, ecx
0x1800478b8  jz      loc_180047951
0x1800478be  cmp     [rsp+98h+var_68], ebp
0x1800478c2  jz      loc_1800479A8
0x1800478c8  mov     rbx, [rsp+98h+pv]
0x1800478cd  cmp     edi, 80040E21h
0x1800478d3  jz      loc_1800479CF
0x1800478d9  mov     rax, [rbx]
0x1800478dc  cmp     [rax+30h], bp
0x1800478e0  jz      loc_1800479EF
0x1800478e6  mov     eax, [rax+38h]
0x1800478e9  mov     [rsi], eax
0x1800478eb  mov     eax, [rbx+8]
0x1800478ee  test    eax, eax
0x1800478f0  jz      short loc_180047927
0x1800478f2  mov     esi, ebp
0x1800478f4  mov     eax, esi
0x1800478f6  lea     rcx, [rax+rax*8]
0x1800478fa  mov     rax, [rbx]
0x1800478fd  lea     rcx, [rcx+6]
0x180047901  lea     rcx, [rax+rcx*8]; pvarg
0x180047905  call    cs:__imp_VariantClear
0x18004790c  nop     dword ptr [rax+rax+00h]
0x180047911  inc     esi
0x180047913  cmp     esi, [rbx+8]
0x180047916  jb      short loc_1800478F4
0x180047918  mov     rcx, [rbx]; pv
0x18004791b  call    cs:__imp_CoTaskMemFree
0x180047922  nop     dword ptr [rax+rax+00h]
0x180047927  mov     rcx, rbx; pv
0x18004792a  call    cs:__imp_CoTaskMemFree
0x180047931  nop     dword ptr [rax+rax+00h]
0x180047936  mov     eax, edi
0x180047938  mov     rcx, [rsp+98h+var_30]
0x18004793d  xor     rcx, rsp; StackCookie
0x180047940  call    __security_check_cookie
0x180047945  add     rsp, 70h
0x180047949  pop     r14
0x18004794b  pop     rdi
0x18004794c  pop     rsi
0x18004794d  pop     rbp
0x18004794e  pop     rbx
0x18004794f  retn
0x180047951  cmp     edi, 80040E21h
0x180047957  jz      loc_1800478BE
0x18004795d  test    byte ptr cs:_bidGblFlags, 2
0x180047964  jz      short loc_180047936
0x180047966  lea     rcx, [rbx+100h]; this
0x18004796d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180047972  cmp     eax, 0FFFFFFFFh
0x180047975  jz      short loc_1800479AC
0x180047977  lea     rcx, [rbx+100h]; this
0x18004797e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180047983  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004798a  lea     r8, aCconnectionGet_34; "<CConnection::GetDBProp|ADO|ERR> %u#, l"...
0x180047991  mov     r9d, eax
0x180047994  mov     [rsp+98h+var_78], 1404h
0x18004799c  mov     edx, 501009h
0x1800479a1  call    _bidTraceW
0x1800479a6  jmp     short loc_180047936
0x1800479a8  xor     eax, eax
0x1800479aa  jmp     short loc_180047938
0x1800479ac  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800479b3  lea     r8, aCconnectionGet_1; "<CConnection::GetDBProp|ADO|ERR>  line "...
0x1800479ba  mov     r9d, 1404h
0x1800479c0  mov     edx, 501009h
0x1800479c5  call    _bidTraceW
0x1800479ca  jmp     loc_180047936
0x1800479cf  test    r14, r14
0x1800479d2  jz      loc_1800478EB
0x1800479d8  mov     rax, [rbx]
0x1800479db  test    rax, rax
0x1800479de  jz      loc_1800478EB
0x1800479e4  mov     eax, [rax+8]
0x1800479e7  mov     [r14], eax
0x1800479ea  jmp     loc_1800478EB
0x1800479ef  mov     [rsi], ebp
0x1800479f1  jmp     loc_1800478EB
```
