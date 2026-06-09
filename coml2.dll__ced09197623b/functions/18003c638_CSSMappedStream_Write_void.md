# CSSMappedStream::Write(void)

- ea: `0x18003c638`
- end: `0x18003c804`
- name: `?Write@CSSMappedStream@@IEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(CSSMappedStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c5e0`
- `0x180059a30`

## callees

- `0x18003c638`
- `0x180042800`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c78c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c78c`

## pseudocode

```c
__int64 __fastcall CSSMappedStream::Write(CSSMappedStream *this)
{
  bool v1; // zf
  __int64 v3; // rcx
  int v4; // edi
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // esi
  unsigned int v8; // ebp
  __int64 v9; // rcx
  unsigned int v10; // esi
  void *v11; // rax
  void *v12; // rbp
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, __int128 *, __int64); // rax
  int v16; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-40h] BYREF

  v1 = *((_DWORD *)this + 12) == 0;
  v16 = 0;
  if ( !v1 && *((_QWORD *)this + 3) )
  {
    v3 = *((_QWORD *)this + 2);
    *(_QWORD *)&v17 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v3 + 40LL))(v3, 0, 0, 0);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 2) + 32LL))(
             *((_QWORD *)this + 2),
             *((_QWORD *)this + 3),
             *((unsigned int *)this + 8),
             &v16);
      if ( v4 )
      {
LABEL_21:
        if ( v4 != -2147286782 )
          return (unsigned int)v4;
LABEL_22:
        *((_DWORD *)this + 12) = 0;
        return (unsigned int)v4;
      }
      v5 = *((_DWORD *)this + 8);
      if ( v16 != v5 )
        return (unsigned int)-2147286789;
      if ( v5 < *((_DWORD *)this + 9) )
      {
        v6 = *((_QWORD *)this + 2);
        *(_QWORD *)&v17 = v5;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 48LL))(v6, v5);
        if ( !v4 )
          *((_DWORD *)this + 9) = *((_DWORD *)this + 8);
      }
      v7 = *((_DWORD *)this + 9);
      v8 = *((_DWORD *)this + 8);
      if ( v8 < v7 )
      {
        v9 = *((_QWORD *)this + 2);
        *(_QWORD *)&v17 = v8;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, v8, 0, 0);
        if ( v4 >= 0 )
        {
          v10 = v7 - v8;
          v11 = CoTaskMemAlloc(v10);
          v12 = v11;
          if ( v11 )
          {
            memset_0(v11, 0, v10);
            v4 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 32LL))(
                   *((_QWORD *)this + 2),
                   v12,
                   v10,
                   0);
            if ( v4 >= 0 )
              CoTaskMemFree(v12);
          }
          else
          {
            v17 = 0;
            while ( 1 )
            {
              v13 = *((_QWORD *)this + 2);
              v14 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v13 + 32LL);
              if ( v10 < 0x10 )
                break;
              v4 = v14(v13, &v17, 16);
              if ( v4 < 0 )
                goto LABEL_21;
              v10 -= 16;
            }
            v4 = ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))v14)(v13, &v17, v10, 0);
          }
        }
      }
    }
    if ( !v4 )
      goto LABEL_22;
    goto LABEL_21;
  }
  return 1;
}

```

## disassembly

```asm
0x18003c638  push    rbx
0x18003c63a  push    rbp
0x18003c63b  push    rsi
0x18003c63c  push    rdi
0x18003c63d  sub     rsp, 58h
0x18003c641  mov     rax, cs:__security_cookie
0x18003c648  xor     rax, rsp
0x18003c64b  mov     [rsp+78h+var_30], rax
0x18003c650  cmp     dword ptr [rcx+30h], 0
0x18003c654  mov     rbx, rcx
0x18003c657  mov     [rsp+78h+var_48], 0
0x18003c65f  jz      loc_18003C7E9
0x18003c665  cmp     qword ptr [rcx+18h], 0
0x18003c66a  jz      loc_18003C7E9
0x18003c670  mov     rcx, [rcx+10h]
0x18003c674  xor     r9d, r9d
0x18003c677  mov     qword ptr [rsp+78h+var_40], 0
0x18003c680  xor     r8d, r8d
0x18003c683  mov     rdx, qword ptr [rsp+78h+var_40]
0x18003c688  mov     rax, [rcx]
0x18003c68b  mov     rax, [rax+28h]
0x18003c68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c694  mov     edi, eax
0x18003c696  test    eax, eax
0x18003c698  js      loc_18003C7D2
0x18003c69e  mov     rcx, [rbx+10h]
0x18003c6a2  lea     r9, [rsp+78h+var_48]
0x18003c6a7  mov     r8d, [rbx+20h]
0x18003c6ab  mov     rdx, [rbx+18h]
0x18003c6af  mov     rax, [rcx]
0x18003c6b2  mov     rax, [rax+20h]
0x18003c6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6bb  mov     edi, eax
0x18003c6bd  test    eax, eax
0x18003c6bf  jnz     loc_18003C7D6
0x18003c6c5  mov     eax, [rbx+20h]
0x18003c6c8  cmp     [rsp+78h+var_48], eax
0x18003c6cc  jz      short loc_18003C6D8
0x18003c6ce  mov     edi, 800300FBh
0x18003c6d3  jmp     loc_18003C7E5
0x18003c6d8  cmp     eax, [rbx+24h]
0x18003c6db  jnb     short loc_18003C70A
0x18003c6dd  mov     rcx, [rbx+10h]
0x18003c6e1  mov     dword ptr [rsp+78h+var_40], eax
0x18003c6e5  mov     dword ptr [rsp+78h+var_40+4], 0
0x18003c6ed  mov     rdx, qword ptr [rsp+78h+var_40]
0x18003c6f2  mov     rax, [rcx]
0x18003c6f5  mov     rax, [rax+30h]
0x18003c6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6fe  mov     edi, eax
0x18003c700  test    eax, eax
0x18003c702  jnz     short loc_18003C70A
0x18003c704  mov     eax, [rbx+20h]
0x18003c707  mov     [rbx+24h], eax
0x18003c70a  mov     esi, [rbx+24h]
0x18003c70d  mov     ebp, [rbx+20h]
0x18003c710  cmp     ebp, esi
0x18003c712  jnb     loc_18003C7D2
0x18003c718  mov     rcx, [rbx+10h]
0x18003c71c  xor     r9d, r9d
0x18003c71f  mov     dword ptr [rsp+78h+var_40+4], 0
0x18003c727  xor     r8d, r8d
0x18003c72a  mov     dword ptr [rsp+78h+var_40], ebp
0x18003c72e  mov     rdx, qword ptr [rsp+78h+var_40]
0x18003c733  mov     rax, [rcx]
0x18003c736  mov     rax, [rax+28h]
0x18003c73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c73f  mov     edi, eax
0x18003c741  test    eax, eax
0x18003c743  js      loc_18003C7D2
0x18003c749  sub     esi, ebp
0x18003c74b  mov     ecx, esi; cb
0x18003c74d  mov     edi, esi
0x18003c74f  call    cs:__imp_CoTaskMemAlloc
0x18003c755  mov     rbp, rax
0x18003c758  test    rax, rax
0x18003c75b  jz      short loc_18003C794
0x18003c75d  mov     r8d, edi; Size
0x18003c760  xor     edx, edx; Val
0x18003c762  mov     rcx, rax; void *
0x18003c765  call    memset_0
0x18003c76a  mov     rcx, [rbx+10h]
0x18003c76e  xor     r9d, r9d
0x18003c771  mov     r8d, esi
0x18003c774  mov     rdx, [rcx]
0x18003c777  mov     rax, [rdx+20h]
0x18003c77b  mov     rdx, rbp
0x18003c77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c783  mov     edi, eax
0x18003c785  test    eax, eax
0x18003c787  js      short loc_18003C7D2
0x18003c789  mov     rcx, rbp; pv
0x18003c78c  call    cs:__imp_CoTaskMemFree
0x18003c792  jmp     short loc_18003C7D2
0x18003c794  xorps   xmm0, xmm0
0x18003c797  movups  [rsp+78h+var_40], xmm0
0x18003c79c  mov     rcx, [rbx+10h]
0x18003c7a0  lea     rdx, [rsp+78h+var_40]
0x18003c7a5  xor     r9d, r9d
0x18003c7a8  mov     rax, [rcx]
0x18003c7ab  mov     rax, [rax+20h]
0x18003c7af  cmp     esi, 10h
0x18003c7b2  jb      short loc_18003C7C8
0x18003c7b4  lea     r8d, [r9+10h]
0x18003c7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7bd  mov     edi, eax
0x18003c7bf  test    eax, eax
0x18003c7c1  js      short loc_18003C7D6
0x18003c7c3  add     esi, 0FFFFFFF0h
0x18003c7c6  jmp     short loc_18003C79C
0x18003c7c8  mov     r8d, esi
0x18003c7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7d0  mov     edi, eax
0x18003c7d2  test    edi, edi
0x18003c7d4  jz      short loc_18003C7DE
0x18003c7d6  cmp     edi, 80030102h
0x18003c7dc  jnz     short loc_18003C7E5
0x18003c7de  mov     dword ptr [rbx+30h], 0
0x18003c7e5  mov     eax, edi
0x18003c7e7  jmp     short loc_18003C7EE
0x18003c7e9  mov     eax, 1
0x18003c7ee  mov     rcx, [rsp+78h+var_30]
0x18003c7f3  xor     rcx, rsp; StackCookie
0x18003c7f6  call    __security_check_cookie
0x18003c7fb  add     rsp, 58h
0x18003c7ff  pop     rdi
0x18003c800  pop     rsi
0x18003c801  pop     rbp
0x18003c802  pop     rbx
0x18003c803  retn
```
