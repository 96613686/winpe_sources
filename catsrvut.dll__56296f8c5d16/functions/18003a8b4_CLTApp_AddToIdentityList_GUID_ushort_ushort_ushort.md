# CLTApp::AddToIdentityList(_GUID,ushort *,ushort *,ushort *)

- ea: `0x18003a8b4`
- end: `0x18003aa6d`
- name: `?AddToIdentityList@CLTApp@@AEAAJU_GUID@@PEAG11@Z`
- size: `441`
- prototype: `__int64 __fastcall(CLTApp *this, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b83c`
- `0x18003bb7c`

## callees

- `0x180001e60`
- `0x18003a88c`
- `0x18003a8b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a8d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a9fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a8d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a9fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTApp::AddToIdentityList(
        CLTApp *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  int v11; // edi
  __int64 v12; // rax
  unsigned __int64 v13; // r12
  unsigned __int16 *v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // r12
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // r14
  unsigned __int16 *v20; // rax
  __int64 v21; // rax

  v9 = CoTaskMemAlloc(0x30u);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)v9 = 0;
    v9[3] = 0;
    v9[4] = 0;
    v9[5] = 0;
    v11 = 0;
    if ( a4 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a4[v12] );
      v13 = v12 + 1;
      v11 = -2147024882;
      v14 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v12 + 1, 2u));
      v10[3] = v14;
      if ( !v14 )
        goto LABEL_12;
      v11 = StringCchCopyW(v14, v13, a4);
      if ( v11 < 0 )
        goto LABEL_12;
    }
    if ( !a5 )
      goto LABEL_13;
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = v15 + 1;
    v11 = -2147024882;
    v17 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v15 + 1, 2u));
    v10[4] = v17;
    if ( v17 && (v11 = StringCchCopyW(v17, v16, a5), v11 >= 0) )
    {
LABEL_13:
      if ( a3 )
      {
        *(_DWORD *)v10 = 1;
        v18 = -1;
        do
          ++v18;
        while ( a3[v18] );
        v19 = v18 + 1;
        v11 = -2147024882;
        v20 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v18 + 1, 2u));
        v10[1] = v20;
        if ( !v20 || (v11 = StringCchCopyW(v20, v19, a3), v11 < 0) )
        {
          IDENTITY::`scalar deleting destructor'((IDENTITY *)v10);
          v10 = 0;
        }
        if ( !v10 )
          return (unsigned int)v11;
      }
      else
      {
        *(struct _GUID *)(v10 + 1) = *a2;
        *(_DWORD *)v10 = 0;
      }
      v21 = *((_QWORD *)this + 8);
      if ( v21 )
        *(_QWORD *)(v21 + 40) = v10;
      else
        *((_QWORD *)this + 7) = v10;
      *((_QWORD *)this + 8) = v10;
    }
    else
    {
LABEL_12:
      IDENTITY::`scalar deleting destructor'((IDENTITY *)v10);
    }
    return (unsigned int)v11;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003a8b4  push    rbx
0x18003a8b6  push    rsi
0x18003a8b7  push    rdi
0x18003a8b8  push    r12
0x18003a8ba  push    r13
0x18003a8bc  push    r14
0x18003a8be  push    r15
0x18003a8c0  sub     rsp, 30h
0x18003a8c4  mov     rsi, rcx
0x18003a8c7  mov     r14, r9
0x18003a8ca  mov     ecx, 30h ; '0'; cb
0x18003a8cf  mov     r15, r8
0x18003a8d2  mov     r13, rdx
0x18003a8d5  call    cs:__imp_CoTaskMemAlloc
0x18003a8db  xor     r12d, r12d
0x18003a8de  mov     [rsp+68h+var_48], rax
0x18003a8e3  mov     rbx, rax
0x18003a8e6  test    rax, rax
0x18003a8e9  jz      loc_18003AA58
0x18003a8ef  mov     [rax], r12d
0x18003a8f2  mov     [rax+18h], r12
0x18003a8f6  mov     [rax+20h], r12
0x18003a8fa  mov     [rax+28h], r12
0x18003a8fe  test    rax, rax
0x18003a901  jz      loc_18003AA58
0x18003a907  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a90b  mov     edi, r12d
0x18003a90e  test    r14, r14
0x18003a911  jz      short loc_18003A962
0x18003a913  mov     rax, rcx
0x18003a916  inc     rax
0x18003a919  cmp     [r14+rax*2], r12w
0x18003a91e  jnz     short loc_18003A916
0x18003a920  lea     r12, [rax+1]
0x18003a924  mov     edi, 8007000Eh
0x18003a929  mov     eax, 2
0x18003a92e  mul     r12
0x18003a931  cmovb   rax, rcx
0x18003a935  mov     rcx, rax; cb
0x18003a938  call    cs:__imp_CoTaskMemAlloc
0x18003a93e  mov     [rbx+18h], rax
0x18003a942  test    rax, rax
0x18003a945  jz      short loc_18003A9BA
0x18003a947  mov     r8, r14; unsigned __int16 *
0x18003a94a  mov     rdx, r12; unsigned __int64
0x18003a94d  mov     rcx, rax; unsigned __int16 *
0x18003a950  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a955  xor     r12d, r12d
0x18003a958  mov     edi, eax
0x18003a95a  test    eax, eax
0x18003a95c  js      short loc_18003A9BA
0x18003a95e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a962  mov     r14, [rsp+68h+arg_20]
0x18003a96a  test    r14, r14
0x18003a96d  jz      short loc_18003A9C7
0x18003a96f  mov     rax, rcx
0x18003a972  inc     rax
0x18003a975  cmp     [r14+rax*2], r12w
0x18003a97a  jnz     short loc_18003A972
0x18003a97c  lea     r12, [rax+1]
0x18003a980  mov     edi, 8007000Eh
0x18003a985  mov     eax, 2
0x18003a98a  mul     r12
0x18003a98d  cmovb   rax, rcx
0x18003a991  mov     rcx, rax; cb
0x18003a994  call    cs:__imp_CoTaskMemAlloc
0x18003a99a  mov     [rbx+20h], rax
0x18003a99e  test    rax, rax
0x18003a9a1  jz      short loc_18003A9BA
0x18003a9a3  mov     r8, r14; unsigned __int16 *
0x18003a9a6  mov     rdx, r12; unsigned __int64
0x18003a9a9  mov     rcx, rax; unsigned __int16 *
0x18003a9ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a9b1  xor     r12d, r12d
0x18003a9b4  mov     edi, eax
0x18003a9b6  test    eax, eax
0x18003a9b8  jns     short loc_18003A9C7
0x18003a9ba  mov     rcx, rbx; this
0x18003a9bd  call    ??_GIDENTITY@@QEAAPEAXI@Z; IDENTITY::`scalar deleting destructor'(uint)
0x18003a9c2  jmp     loc_18003AA54
0x18003a9c7  test    r15, r15
0x18003a9ca  jz      short loc_18003AA30
0x18003a9cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a9d0  mov     dword ptr [rbx], 1
0x18003a9d6  mov     rcx, r8
0x18003a9d9  inc     rcx
0x18003a9dc  cmp     [r15+rcx*2], r12w
0x18003a9e1  jnz     short loc_18003A9D9
0x18003a9e3  lea     r14, [rcx+1]
0x18003a9e7  mov     eax, 2
0x18003a9ec  mul     r14
0x18003a9ef  mov     edi, 8007000Eh
0x18003a9f4  cmovb   rax, r8
0x18003a9f8  mov     rcx, rax; cb
0x18003a9fb  call    cs:__imp_CoTaskMemAlloc
0x18003aa01  mov     [rbx+8], rax
0x18003aa05  test    rax, rax
0x18003aa08  jz      short loc_18003AA1E
0x18003aa0a  mov     r8, r15; unsigned __int16 *
0x18003aa0d  mov     rdx, r14; unsigned __int64
0x18003aa10  mov     rcx, rax; unsigned __int16 *
0x18003aa13  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003aa18  mov     edi, eax
0x18003aa1a  test    eax, eax
0x18003aa1c  jns     short loc_18003AA29
0x18003aa1e  mov     rcx, rbx; this
0x18003aa21  call    ??_GIDENTITY@@QEAAPEAXI@Z; IDENTITY::`scalar deleting destructor'(uint)
0x18003aa26  mov     rbx, r12
0x18003aa29  test    rbx, rbx
0x18003aa2c  jz      short loc_18003AA54
0x18003aa2e  jmp     short loc_18003AA3D
0x18003aa30  movaps  xmm0, xmmword ptr [r13+0]
0x18003aa35  movdqu  xmmword ptr [rbx+8], xmm0
0x18003aa3a  mov     [rbx], r12d
0x18003aa3d  mov     rax, [rsi+40h]
0x18003aa41  test    rax, rax
0x18003aa44  jz      short loc_18003AA4C
0x18003aa46  mov     [rax+28h], rbx
0x18003aa4a  jmp     short loc_18003AA50
0x18003aa4c  mov     [rsi+38h], rbx
0x18003aa50  mov     [rsi+40h], rbx
0x18003aa54  mov     eax, edi
0x18003aa56  jmp     short loc_18003AA5D
0x18003aa58  mov     eax, 8007000Eh
0x18003aa5d  add     rsp, 30h
0x18003aa61  pop     r15
0x18003aa63  pop     r14
0x18003aa65  pop     r13
0x18003aa67  pop     r12
0x18003aa69  pop     rdi
0x18003aa6a  pop     rsi
0x18003aa6b  pop     rbx
0x18003aa6c  retn
```
