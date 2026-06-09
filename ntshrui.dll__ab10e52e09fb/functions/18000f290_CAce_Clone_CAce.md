# CAce::Clone(CAce * *)

- ea: `0x18000f290`
- end: `0x18000f49b`
- name: `?Clone@CAce@@QEBAJPEAPEAV1@@Z`
- size: `523`
- prototype: `__int64 __fastcall(CAce *__hidden this, struct CAce **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034090`
- `0x18005b360`
- `0x18005b52c`

## callees

- `0x1800098dc`
- `0x18000f290`
- `0x18000f4b0`
- `0x1800259bc`
- `0x18002637c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f32c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f32c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f36d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f36d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f33d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f44d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f33d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f44d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f352`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f46e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f352`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f46e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f43b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f43b`
- `ntdll!RtlMapGenericMask` at `0x18000f3bb`
- `ntdll!RtlMapGenericMask` at `0x18000f3bb`

## pseudocode

```c
__int64 __fastcall CAce::Clone(CAce *this, struct CAce **a2)
{
  _QWORD *v4; // rax
  unsigned int v5; // edx
  _QWORD *v6; // rbx
  void *v7; // rbp
  unsigned int v8; // r13d
  int v9; // eax
  int Error; // edi
  DWORD LengthSid; // r12d
  HLOCAL v12; // rax
  void *v13; // r15
  char v14; // cl
  unsigned int v15; // eax
  DWORD v17; // edx
  HLOCAL v18; // rax
  void *Src; // [rsp+20h] [rbp-48h]
  char v20; // [rsp+78h] [rbp+10h]
  char v21; // [rsp+80h] [rbp+18h]
  int v22; // [rsp+88h] [rbp+20h]

  *a2 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v4;
  if ( v4 )
  {
    *v4 = 0x80000;
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
    v7 = (void *)*((_QWORD *)this + 1);
    if ( !v7 )
    {
      Error = -2147024809;
      goto LABEL_15;
    }
    v8 = *((unsigned __int16 *)this + 1);
    Src = (void *)*((_QWORD *)this + 2);
    v20 = *(_BYTE *)this;
    v21 = *((_BYTE *)this + 1);
    v9 = *((_DWORD *)this + 1);
    Error = -2147024809;
    v22 = v9;
    if ( IsValidSid(v7) )
    {
      LengthSid = GetLengthSid(v7);
      Error = -2147024882;
      v12 = LocalAlloc(0x40u, LengthSid);
      v13 = v12;
      if ( v12 )
      {
        if ( CopySid(LengthSid, v12, v7) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
            LocalFree(v13);
            goto LABEL_15;
          }
        }
        v6[1] = v13;
        if ( Src )
        {
          v17 = GetLengthSid(v7) + 8;
          if ( v8 > v17 )
          {
            *((_DWORD *)v6 + 6) = v8 - v17;
            v18 = LocalAlloc(0x40u, v8 - v17);
            v6[2] = v18;
            if ( !v18 )
            {
              Error = -2147024882;
              goto LABEL_15;
            }
            memcpy_0(v18, Src, *((unsigned int *)v6 + 6));
          }
        }
        *(_BYTE *)v6 = v20;
        *((_BYTE *)v6 + 1) = v21;
        *((_DWORD *)v6 + 1) = v22;
        *((_WORD *)v6 + 1) = v8;
        RtlMapGenericMask((PACCESS_MASK)v6 + 1, (PGENERIC_MAPPING)&GenericMapping);
        v14 = *(_BYTE *)v6;
        v15 = 0x80000000;
        *((_DWORD *)v6 + 7) = 0x80000000;
        if ( !v14 || v14 == 9 )
        {
          v15 = -2147483647;
          *((_DWORD *)v6 + 7) = -2147483647;
        }
        if ( (*((_BYTE *)v6 + 1) & 0x10) != 0 )
        {
          *((_DWORD *)v6 + 7) = v15 | 0x20;
LABEL_12:
          *a2 = (struct CAce *)v6;
          return (unsigned int)Error;
        }
      }
    }
    if ( Error >= 0 )
      goto LABEL_12;
LABEL_15:
    CAce::`scalar deleting destructor'((CAce *)v6, v5);
    return (unsigned int)Error;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f290  push    rbx
0x18000f292  push    rbp
0x18000f293  push    rsi
0x18000f294  push    rdi
0x18000f295  sub     rsp, 48h
0x18000f299  mov     rsi, rdx
0x18000f29c  mov     rdi, rcx
0x18000f29f  xor     ebp, ebp
0x18000f2a1  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f2a6  mov     [rdx], rbp
0x18000f2a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f2b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f2b5  mov     [rsp+68h+arg_8], rax
0x18000f2ba  mov     rbx, rax
0x18000f2bd  test    rax, rax
0x18000f2c0  jz      loc_18000F41B
0x18000f2c6  mov     [rsp+68h+var_30], r14
0x18000f2cb  mov     [rsp+68h+arg_0], r12
0x18000f2d0  mov     qword ptr [rax], 80000h
0x18000f2d7  mov     [rax+8], rbp
0x18000f2db  mov     [rax+10h], rbp
0x18000f2df  mov     [rax+18h], rbp
0x18000f2e3  mov     rbp, [rdi+8]
0x18000f2e7  mov     [rsp+68h+var_28], r13
0x18000f2ec  mov     [rsp+68h+var_38], r15
0x18000f2f1  test    rbp, rbp
0x18000f2f4  jz      loc_18000F443
0x18000f2fa  mov     rax, [rdi+10h]
0x18000f2fe  mov     rcx, rbp; pSid
0x18000f301  movzx   r13d, word ptr [rdi+2]
0x18000f306  mov     [rsp+68h+Src], rax
0x18000f30b  movzx   eax, byte ptr [rdi]
0x18000f30e  mov     byte ptr [rsp+68h+arg_8], al
0x18000f312  movzx   eax, byte ptr [rdi+1]
0x18000f316  mov     [rsp+68h+arg_10], al
0x18000f31d  mov     eax, [rdi+4]
0x18000f320  mov     edi, 80070057h
0x18000f325  mov     [rsp+68h+arg_18], eax
0x18000f32c  call    cs:__imp_IsValidSid
0x18000f332  test    eax, eax
0x18000f334  jz      loc_18000F406
0x18000f33a  mov     rcx, rbp; pSid
0x18000f33d  call    cs:__imp_GetLengthSid
0x18000f343  mov     edx, eax; uBytes
0x18000f345  mov     ecx, 40h ; '@'; uFlags
0x18000f34a  mov     r12d, eax
0x18000f34d  mov     edi, 8007000Eh
0x18000f352  call    cs:__imp_LocalAlloc
0x18000f358  mov     r15, rax
0x18000f35b  test    rax, rax
0x18000f35e  jz      loc_18000F406
0x18000f364  mov     r8, rbp; pSourceSid
0x18000f367  mov     rdx, rax; pDestinationSid
0x18000f36a  mov     ecx, r12d; nDestinationSidLength
0x18000f36d  call    cs:__imp_CopySid
0x18000f373  test    eax, eax
0x18000f375  jz      loc_18000F429
0x18000f37b  xor     edi, edi
0x18000f37d  mov     [rbx+8], r15
0x18000f381  mov     r15, [rsp+68h+Src]
0x18000f386  test    r15, r15
0x18000f389  jnz     loc_18000F44A
0x18000f38f  movzx   eax, byte ptr [rsp+68h+arg_8]
0x18000f394  lea     rdx, GenericMapping; GenericMapping
0x18000f39b  mov     [rbx], al
0x18000f39d  lea     rcx, [rbx+4]; AccessMask
0x18000f3a1  movzx   eax, [rsp+68h+arg_10]
0x18000f3a9  mov     [rbx+1], al
0x18000f3ac  mov     eax, [rsp+68h+arg_18]
0x18000f3b3  mov     [rbx+4], eax
0x18000f3b6  mov     [rbx+2], r13w
0x18000f3bb  call    cs:__imp_RtlMapGenericMask
0x18000f3c1  movzx   ecx, byte ptr [rbx]
0x18000f3c4  mov     eax, 80000000h
0x18000f3c9  mov     [rbx+1Ch], eax
0x18000f3cc  test    cl, cl
0x18000f3ce  jnz     short loc_18000F414
0x18000f3d0  mov     eax, 80000001h
0x18000f3d5  mov     [rbx+1Ch], eax
0x18000f3d8  test    byte ptr [rbx+1], 10h
0x18000f3dc  jz      short loc_18000F406
0x18000f3de  or      eax, 20h
0x18000f3e1  mov     [rbx+1Ch], eax
0x18000f3e4  mov     [rsi], rbx
0x18000f3e7  mov     r12, [rsp+68h+arg_0]
0x18000f3ec  mov     eax, edi
0x18000f3ee  mov     r13, [rsp+68h+var_28]
0x18000f3f3  mov     r15, [rsp+68h+var_38]
0x18000f3f8  mov     r14, [rsp+68h+var_30]
0x18000f3fd  add     rsp, 48h
0x18000f401  pop     rdi
0x18000f402  pop     rsi
0x18000f403  pop     rbp
0x18000f404  pop     rbx
0x18000f405  retn
0x18000f406  test    edi, edi
0x18000f408  jns     short loc_18000F3E4
0x18000f40a  mov     rcx, rbx; this
0x18000f40d  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000f412  jmp     short loc_18000F3E7
0x18000f414  cmp     cl, 9
0x18000f417  jnz     short loc_18000F3D8
0x18000f419  jmp     short loc_18000F3D0
0x18000f41b  mov     eax, 8007000Eh
0x18000f420  add     rsp, 48h
0x18000f424  pop     rdi
0x18000f425  pop     rsi
0x18000f426  pop     rbp
0x18000f427  pop     rbx
0x18000f428  retn
0x18000f429  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f42e  mov     edi, eax
0x18000f430  test    eax, eax
0x18000f432  jns     loc_18000F37D
0x18000f438  mov     rcx, r15; hMem
0x18000f43b  call    cs:__imp_LocalFree
0x18000f441  jmp     short loc_18000F40A
0x18000f443  mov     edi, 80070057h
0x18000f448  jmp     short loc_18000F40A
0x18000f44a  mov     rcx, rbp; pSid
0x18000f44d  call    cs:__imp_GetLengthSid
0x18000f453  lea     edx, [rax+8]
0x18000f456  mov     eax, r13d
0x18000f459  cmp     r13d, edx
0x18000f45c  jbe     loc_18000F38F
0x18000f462  sub     eax, edx
0x18000f464  mov     ecx, 40h ; '@'; uFlags
0x18000f469  mov     edx, eax; uBytes
0x18000f46b  mov     [rbx+18h], edx
0x18000f46e  call    cs:__imp_LocalAlloc
0x18000f474  mov     [rbx+10h], rax
0x18000f478  test    rax, rax
0x18000f47b  jz      short loc_18000F491
0x18000f47d  mov     r8d, [rbx+18h]; Size
0x18000f481  mov     rdx, r15; Src
0x18000f484  mov     rcx, rax; void *
0x18000f487  call    memcpy_0
0x18000f48c  jmp     loc_18000F38F
0x18000f491  mov     edi, 8007000Eh
0x18000f496  jmp     loc_18000F40A
```
