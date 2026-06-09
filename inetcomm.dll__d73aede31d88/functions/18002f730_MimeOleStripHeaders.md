# MimeOleStripHeaders

- ea: `0x18002f730`
- end: `0x18002f9bd`
- name: `MimeOleStripHeaders`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005748`
- `0x180021140`
- `0x18002f730`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrStreamSeekSet` at `0x18002f872`
- `MSOERT2!HrStreamSeekSet` at `0x18002f90c`
- `MSOERT2!HrStreamSeekSet` at `0x18002f872`
- `MSOERT2!HrStreamSeekSet` at `0x18002f90c`
- `MSOERT2!HrCopyStreamCB` at `0x18002f898`
- `MSOERT2!HrCopyStreamCB` at `0x18002f898`
- `MSOERT2!HrCopyStream` at `0x18002f922`
- `MSOERT2!HrCopyStream` at `0x18002f922`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002f948`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002f948`

## pseudocode

```c
__int64 __fastcall MimeOleStripHeaders(__int64 a1, __int64 a2, __int64 a3, __int64 a4, IStream **a5)
{
  HRESULT v9; // ebx
  unsigned int v10; // esi
  IStream *v11; // rdi
  unsigned int v12; // r14d
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  IStream *pstm; // [rsp+48h] [rbp-38h] BYREF
  __int128 v21; // [rsp+50h] [rbp-30h] BYREF
  __int128 v22; // [rsp+60h] [rbp-20h] BYREF

  v18 = 0;
  v17 = 0;
  pstm = 0;
  v19 = 0;
  v22 = 0;
  v21 = 0;
  if ( !a1 || !a2 || !a3 || !a5 )
    return 2147942487LL;
  *a5 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, &v17, 0);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)a1 + 128LL))(
           a1,
           a2,
           &IID_IMimeHeaderTable,
           &v18);
    if ( v9 >= 0 )
    {
      *(_QWORD *)&v21 = a3;
      v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, &v21, &v19);
      if ( v9 >= 0 )
      {
        v10 = 0;
        v9 = MimeOleCreateVirtualStream(&pstm);
        if ( v9 >= 0 )
        {
          v11 = pstm;
          while ( 1 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v18 + 120LL))(v18, v19, &v22);
            if ( v9 < 0 )
              break;
            v12 = DWORD1(v22) - v10;
            v9 = HrStreamSeekSet(v17, v10);
            if ( v9 < 0 )
              break;
            v9 = HrCopyStreamCB(v17, v11, v12, 0, 0);
            if ( v9 < 0 )
              break;
            v10 = HIDWORD(v22);
            v13 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v18 + 72LL))(v18, &v21, &v19);
            v9 = v13;
            if ( v13 < 0 )
            {
              if ( v13 == -2146644475 )
              {
                if ( !a4 )
                  goto LABEL_30;
                v14 = -1;
                do
                  ++v14;
                while ( *(_BYTE *)(a4 + v14) );
                v9 = ((__int64 (__fastcall *)(IStream *, __int64, __int64, _QWORD))v11->lpVtbl->Write)(v11, a4, v14, 0);
                if ( v9 >= 0 )
                {
LABEL_30:
                  v9 = HrStreamSeekSet(v17, v10);
                  if ( v9 >= 0 )
                  {
                    v9 = HrCopyStream(v17, v11, 0);
                    if ( v9 >= 0 )
                    {
                      v9 = ((__int64 (__fastcall *)(IStream *, _QWORD))v11->lpVtbl->Commit)(v11, 0);
                      if ( v9 >= 0 )
                      {
                        v9 = IStream_Reset(v11);
                        if ( v9 >= 0 )
                        {
                          *a5 = v11;
                          ((void (__fastcall *)(IStream *))v11->lpVtbl->AddRef)(v11);
                        }
                      }
                    }
                  }
                }
              }
              break;
            }
          }
        }
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IStream>(&v17);
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  OE_SafeReleaseAndNullPtr<IStream>(&pstm);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002f730  push    rbp
0x18002f732  push    rbx
0x18002f733  push    rsi
0x18002f734  push    rdi
0x18002f735  push    r12
0x18002f737  push    r14
0x18002f739  push    r15
0x18002f73b  mov     rbp, rsp
0x18002f73e  sub     rsp, 80h
0x18002f745  mov     rax, cs:__security_cookie
0x18002f74c  xor     rax, rsp
0x18002f74f  mov     [rbp+var_10], rax
0x18002f753  mov     r12, [rbp+arg_20]
0x18002f757  xorps   xmm0, xmm0
0x18002f75a  mov     [rbp+var_48], 0
0x18002f762  xorps   xmm1, xmm1
0x18002f765  mov     [rbp+var_50], 0
0x18002f76d  mov     r15, r9
0x18002f770  mov     [rbp+pstm], 0
0x18002f778  mov     r14, r8
0x18002f77b  mov     [rbp+var_40], 0
0x18002f783  mov     rsi, rdx
0x18002f786  mov     rdi, rcx
0x18002f789  movups  [rbp+var_20], xmm0
0x18002f78d  movups  [rbp+var_30], xmm1
0x18002f791  test    rcx, rcx
0x18002f794  jz      loc_18002F99A
0x18002f79a  test    rdx, rdx
0x18002f79d  jz      loc_18002F99A
0x18002f7a3  test    r8, r8
0x18002f7a6  jz      loc_18002F99A
0x18002f7ac  test    r12, r12
0x18002f7af  jz      loc_18002F99A
0x18002f7b5  mov     qword ptr [r12], 0
0x18002f7bd  lea     rdx, [rbp+var_50]
0x18002f7c1  mov     rax, [rcx]
0x18002f7c4  xor     r8d, r8d
0x18002f7c7  mov     rax, [rax+48h]
0x18002f7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7d0  mov     ebx, eax
0x18002f7d2  test    eax, eax
0x18002f7d4  js      loc_18002F967
0x18002f7da  mov     rax, [rdi]
0x18002f7dd  lea     r9, [rbp+var_48]
0x18002f7e1  lea     r8, IID_IMimeHeaderTable
0x18002f7e8  mov     rdx, rsi
0x18002f7eb  mov     rcx, rdi
0x18002f7ee  mov     rax, [rax+80h]
0x18002f7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7fa  mov     ebx, eax
0x18002f7fc  test    eax, eax
0x18002f7fe  js      loc_18002F967
0x18002f804  mov     rcx, [rbp+var_48]
0x18002f808  lea     r8, [rbp+var_40]
0x18002f80c  mov     qword ptr [rbp+var_30], r14
0x18002f810  lea     rdx, [rbp+var_30]
0x18002f814  mov     rax, [rcx]
0x18002f817  mov     rax, [rax+40h]
0x18002f81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f820  mov     ebx, eax
0x18002f822  test    eax, eax
0x18002f824  js      loc_18002F967
0x18002f82a  lea     rcx, [rbp+pstm]
0x18002f82e  xor     esi, esi
0x18002f830  call    MimeOleCreateVirtualStream
0x18002f835  mov     ebx, eax
0x18002f837  test    eax, eax
0x18002f839  js      loc_18002F967
0x18002f83f  mov     rdi, [rbp+pstm]
0x18002f843  mov     rcx, [rbp+var_48]
0x18002f847  lea     r8, [rbp+var_20]
0x18002f84b  mov     rdx, [rbp+var_40]
0x18002f84f  mov     rax, [rcx]
0x18002f852  mov     rax, [rax+78h]
0x18002f856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f85b  mov     ebx, eax
0x18002f85d  test    eax, eax
0x18002f85f  js      loc_18002F967
0x18002f865  mov     r14d, dword ptr [rbp+var_20+4]
0x18002f869  mov     edx, esi
0x18002f86b  mov     rcx, [rbp+var_50]
0x18002f86f  sub     r14d, esi
0x18002f872  call    cs:__imp_HrStreamSeekSet
0x18002f878  mov     ebx, eax
0x18002f87a  test    eax, eax
0x18002f87c  js      loc_18002F967
0x18002f882  mov     rcx, [rbp+var_50]
0x18002f886  xor     r9d, r9d
0x18002f889  mov     r8d, r14d
0x18002f88c  mov     rdx, rdi
0x18002f88f  mov     [rsp+80h+var_60], 0
0x18002f898  call    cs:__imp_HrCopyStreamCB
0x18002f89e  mov     ebx, eax
0x18002f8a0  test    eax, eax
0x18002f8a2  js      loc_18002F967
0x18002f8a8  mov     rcx, [rbp+var_48]
0x18002f8ac  lea     r8, [rbp+var_40]
0x18002f8b0  mov     esi, dword ptr [rbp+var_20+0Ch]
0x18002f8b3  lea     rdx, [rbp+var_30]
0x18002f8b7  mov     rax, [rcx]
0x18002f8ba  mov     rax, [rax+48h]
0x18002f8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8c3  mov     ebx, eax
0x18002f8c5  test    eax, eax
0x18002f8c7  jns     loc_18002F843
0x18002f8cd  cmp     eax, 800CCE05h
0x18002f8d2  jnz     loc_18002F967
0x18002f8d8  test    r15, r15
0x18002f8db  jz      short loc_18002F906
0x18002f8dd  mov     rax, [rdi]
0x18002f8e0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f8e4  inc     r8
0x18002f8e7  cmp     byte ptr [r15+r8], 0
0x18002f8ec  jnz     short loc_18002F8E4
0x18002f8ee  mov     rax, [rax+20h]
0x18002f8f2  xor     r9d, r9d
0x18002f8f5  mov     rdx, r15
0x18002f8f8  mov     rcx, rdi
0x18002f8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f900  mov     ebx, eax
0x18002f902  test    eax, eax
0x18002f904  js      short loc_18002F967
0x18002f906  mov     rcx, [rbp+var_50]
0x18002f90a  mov     edx, esi
0x18002f90c  call    cs:__imp_HrStreamSeekSet
0x18002f912  mov     ebx, eax
0x18002f914  test    eax, eax
0x18002f916  js      short loc_18002F967
0x18002f918  mov     rcx, [rbp+var_50]
0x18002f91c  xor     r8d, r8d
0x18002f91f  mov     rdx, rdi
0x18002f922  call    cs:__imp_HrCopyStream
0x18002f928  mov     ebx, eax
0x18002f92a  test    eax, eax
0x18002f92c  js      short loc_18002F967
0x18002f92e  mov     rax, [rdi]
0x18002f931  xor     edx, edx
0x18002f933  mov     rcx, rdi
0x18002f936  mov     rax, [rax+40h]
0x18002f93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f93f  mov     ebx, eax
0x18002f941  test    eax, eax
0x18002f943  js      short loc_18002F967
0x18002f945  mov     rcx, rdi; pstm
0x18002f948  call    cs:__imp_IStream_Reset
0x18002f94e  mov     ebx, eax
0x18002f950  test    eax, eax
0x18002f952  js      short loc_18002F967
0x18002f954  mov     [r12], rdi
0x18002f958  mov     rcx, rdi
0x18002f95b  mov     rax, [rdi]
0x18002f95e  mov     rax, [rax+8]
0x18002f962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f967  lea     rcx, [rbp+var_50]
0x18002f96b  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18002f970  mov     rcx, [rbp+var_48]
0x18002f974  test    rcx, rcx
0x18002f977  jz      short loc_18002F98D
0x18002f979  mov     [rbp+var_48], 0
0x18002f981  mov     rax, [rcx]
0x18002f984  mov     rax, [rax+10h]
0x18002f988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f98d  lea     rcx, [rbp+pstm]
0x18002f991  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18002f996  mov     eax, ebx
0x18002f998  jmp     short loc_18002F99F
0x18002f99a  mov     eax, 80070057h
0x18002f99f  mov     rcx, [rbp+var_10]
0x18002f9a3  xor     rcx, rsp; StackCookie
0x18002f9a6  call    __security_check_cookie
0x18002f9ab  add     rsp, 80h
0x18002f9b2  pop     r15
0x18002f9b4  pop     r14
0x18002f9b6  pop     r12
0x18002f9b8  pop     rdi
0x18002f9b9  pop     rsi
0x18002f9ba  pop     rbx
0x18002f9bb  pop     rbp
0x18002f9bc  retn
```
