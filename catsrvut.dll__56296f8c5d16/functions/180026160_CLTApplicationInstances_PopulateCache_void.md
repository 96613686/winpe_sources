# CLTApplicationInstances::PopulateCache(void)

- ea: `0x180026160`
- end: `0x1800263cb`
- name: `?PopulateCache@CLTApplicationInstances@@UEAAJXZ`
- size: `619`
- prototype: `__int64 __fastcall(CLTApplicationInstances *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180026160`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800261c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800261c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263b6`

## pseudocode

```c
__int64 __fastcall CLTApplicationInstances::PopulateCache(CLTApplicationInstances *this)
{
  char *v1; // r14
  __int64 v2; // rax
  HRESULT v4; // ebx
  unsigned int v5; // esi
  __int64 v6; // r15
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+80h] [rbp+38h] BYREF
  int v10; // [rsp+88h] [rbp+40h]
  int v11; // [rsp+90h] [rbp+48h]
  LPVOID pv; // [rsp+98h] [rbp+50h] BYREF

  v1 = (char *)this + 8;
  ppv = 0;
  v2 = *((_QWORD *)this + 1);
  pv = 0;
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(v2 + 32))((char *)this + 8, 0);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(&CLSID_CatalogServer, 0, 5u, &IID_IApplicationControl2, &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, char *, char *, unsigned int *, LPVOID *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             (char *)this + 56,
             (char *)this + 40,
             &v9,
             &pv);
      if ( v4 >= 0 )
      {
        v5 = 0;
        v11 = 1;
        v10 = 0;
        if ( v9 )
        {
          while ( 1 )
          {
            v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
            if ( v4 < 0 )
              break;
            v6 = 60LL * v5;
            v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   0,
                   0,
                   (char *)pv + v6 + 32);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   1,
                   0,
                   (char *)pv + v6);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   2,
                   0,
                   (char *)pv + v6 + 16);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   3,
                   0,
                   (char *)pv + v6 + 48);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   4);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                   *((_QWORD *)this + 4),
                   5);
            if ( v4 < 0 )
              break;
            v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
            if ( v4 < 0 )
              break;
            if ( ++v5 >= v9 )
              goto LABEL_14;
          }
        }
        else
        {
LABEL_14:
          v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 40LL))(v1);
        }
      }
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026160  push    rbp
0x180026162  push    rbx
0x180026163  push    rsi
0x180026164  push    rdi
0x180026165  push    r14
0x180026167  push    r15
0x180026169  mov     rbp, rsp
0x18002616c  sub     rsp, 48h
0x180026170  lea     r14, [rcx+8]
0x180026174  mov     [rbp+var_18], 0
0x18002617c  mov     rax, [r14]
0x18002617f  mov     rdi, rcx
0x180026182  xor     edx, edx
0x180026184  mov     [rbp+pv], 0
0x18002618c  mov     rcx, r14
0x18002618f  mov     [rbp+arg_0], 0
0x180026196  mov     rax, [rax+20h]
0x18002619a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002619f  mov     ebx, eax
0x1800261a1  test    eax, eax
0x1800261a3  js      loc_180026395
0x1800261a9  xor     edx, edx; pUnkOuter
0x1800261ab  lea     rax, [rbp+var_18]
0x1800261af  lea     r9, IID_IApplicationControl2; riid
0x1800261b6  mov     [rsp+48h+ppv], rax; ppv
0x1800261bb  lea     rcx, CLSID_CatalogServer; rclsid
0x1800261c2  lea     r8d, [rdx+5]; dwClsContext
0x1800261c6  call    cs:__imp_CoCreateInstance
0x1800261cc  mov     ebx, eax
0x1800261ce  test    eax, eax
0x1800261d0  js      loc_180026395
0x1800261d6  mov     rcx, [rbp+var_18]
0x1800261da  lea     r9, [rbp+pv]
0x1800261de  mov     [rsp+48h+ppv], r9
0x1800261e3  lea     r8, [rdi+28h]
0x1800261e7  lea     rdx, [rdi+38h]
0x1800261eb  lea     r9, [rbp+arg_0]
0x1800261ef  mov     rax, [rcx]
0x1800261f2  mov     rax, [rax+38h]
0x1800261f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261fb  mov     ebx, eax
0x1800261fd  test    eax, eax
0x1800261ff  js      loc_180026395
0x180026205  xor     esi, esi
0x180026207  mov     [rbp+arg_10], 1
0x18002620e  mov     [rbp+arg_8], 0
0x180026215  cmp     [rbp+arg_0], esi
0x180026218  jbe     loc_180026384
0x18002621e  mov     rcx, [rdi+20h]
0x180026222  mov     rax, [rcx]
0x180026225  mov     rax, [rax+78h]
0x180026229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002622e  mov     ebx, eax
0x180026230  test    eax, eax
0x180026232  js      loc_180026395
0x180026238  mov     rcx, [rdi+20h]
0x18002623c  xor     r8d, r8d
0x18002623f  mov     r9, [rbp+pv]
0x180026243  mov     eax, esi
0x180026245  add     r9, 20h ; ' '
0x180026249  imul    r15, rax, 3Ch ; '<'
0x18002624d  mov     rdx, [rcx]
0x180026250  add     r9, r15
0x180026253  mov     rax, [rdx+0A0h]
0x18002625a  xor     edx, edx
0x18002625c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026261  mov     ebx, eax
0x180026263  test    eax, eax
0x180026265  js      loc_180026395
0x18002626b  mov     rcx, [rdi+20h]
0x18002626f  xor     r8d, r8d
0x180026272  mov     r9, [rbp+pv]
0x180026276  add     r9, r15
0x180026279  mov     rdx, [rcx]
0x18002627c  mov     rax, [rdx+0A0h]
0x180026283  lea     edx, [r8+1]
0x180026287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002628c  mov     ebx, eax
0x18002628e  test    eax, eax
0x180026290  js      loc_180026395
0x180026296  mov     rcx, [rdi+20h]
0x18002629a  xor     r8d, r8d
0x18002629d  mov     r9, [rbp+pv]
0x1800262a1  add     r9, 10h
0x1800262a5  add     r9, r15
0x1800262a8  mov     rdx, [rcx]
0x1800262ab  mov     rax, [rdx+0A0h]
0x1800262b2  lea     edx, [r8+2]
0x1800262b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262bb  mov     ebx, eax
0x1800262bd  test    eax, eax
0x1800262bf  js      loc_180026395
0x1800262c5  mov     rcx, [rdi+20h]
0x1800262c9  xor     r8d, r8d
0x1800262cc  mov     r9, [rbp+pv]
0x1800262d0  add     r9, 30h ; '0'
0x1800262d4  add     r9, r15
0x1800262d7  mov     rdx, [rcx]
0x1800262da  mov     rax, [rdx+0A0h]
0x1800262e1  lea     edx, [r8+3]
0x1800262e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262ea  mov     ebx, eax
0x1800262ec  test    eax, eax
0x1800262ee  js      loc_180026395
0x1800262f4  mov     rax, [rbp+pv]
0x1800262f8  lea     r8, [rbp+arg_10]
0x1800262fc  mov     rcx, [rdi+20h]
0x180026300  lea     r9, [rbp+arg_8]
0x180026304  cmp     dword ptr [r15+rax+34h], 0
0x18002630a  mov     rdx, [rcx]
0x18002630d  cmovnz  r9, r8
0x180026311  xor     r8d, r8d
0x180026314  mov     rax, [rdx+0A0h]
0x18002631b  lea     edx, [r8+4]
0x18002631f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026324  mov     ebx, eax
0x180026326  test    eax, eax
0x180026328  js      short loc_180026395
0x18002632a  mov     rax, [rbp+pv]
0x18002632e  lea     r8, [rbp+arg_10]
0x180026332  mov     rcx, [rdi+20h]
0x180026336  lea     r9, [rbp+arg_8]
0x18002633a  cmp     dword ptr [r15+rax+38h], 0
0x180026340  mov     rdx, [rcx]
0x180026343  cmovnz  r9, r8
0x180026347  xor     r8d, r8d
0x18002634a  mov     rax, [rdx+0A0h]
0x180026351  lea     edx, [r8+5]
0x180026355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002635a  mov     ebx, eax
0x18002635c  test    eax, eax
0x18002635e  js      short loc_180026395
0x180026360  mov     rcx, [rdi+20h]
0x180026364  mov     rax, [rcx]
0x180026367  mov     rax, [rax+90h]
0x18002636e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026373  mov     ebx, eax
0x180026375  test    eax, eax
0x180026377  js      short loc_180026395
0x180026379  inc     esi
0x18002637b  cmp     esi, [rbp+arg_0]
0x18002637e  jb      loc_18002621E
0x180026384  mov     rax, [r14]
0x180026387  mov     rcx, r14
0x18002638a  mov     rax, [rax+28h]
0x18002638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026393  mov     ebx, eax
0x180026395  mov     rcx, [rbp+var_18]
0x180026399  test    rcx, rcx
0x18002639c  jz      short loc_1800263B2
0x18002639e  mov     rax, [rcx]
0x1800263a1  mov     rax, [rax+10h]
0x1800263a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263aa  mov     [rbp+var_18], 0
0x1800263b2  mov     rcx, [rbp+pv]; pv
0x1800263b6  call    cs:__imp_CoTaskMemFree
0x1800263bc  mov     eax, ebx
0x1800263be  add     rsp, 48h
0x1800263c2  pop     r15
0x1800263c4  pop     r14
0x1800263c6  pop     rdi
0x1800263c7  pop     rsi
0x1800263c8  pop     rbx
0x1800263c9  pop     rbp
0x1800263ca  retn
```
