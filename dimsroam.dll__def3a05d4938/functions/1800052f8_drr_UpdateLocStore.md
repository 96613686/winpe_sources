# _drr_UpdateLocStore

- ea: `0x1800052f8`
- end: `0x180005426`
- name: `_drr_UpdateLocStore`
- size: `302`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000542c`

## callees

- `0x1800052f8`
- `0x18000e010`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x1800053da`
- `CRYPT32!CertCloseStore` at `0x1800053da`
- `CRYPT32!CertOpenStore` at `0x1800053ca`
- `CRYPT32!CertOpenStore` at `0x1800053ca`

## pseudocode

```c
__int64 __fastcall drr_UpdateLocStore(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v3; // r14
  unsigned int v4; // ebp
  unsigned int v5; // esi
  int v6; // r12d
  __int64 i; // rdi
  __int64 v10; // rbx
  unsigned int v11; // ecx
  HCERTSTORE v12; // rax

  v3 = *a2;
  v4 = 0;
  v5 = *((_DWORD *)a2 + 2);
  v6 = 0;
  while ( 1 )
  {
    for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
    {
      v10 = *(_QWORD *)(v3 + 8 * i);
      if ( (*(_BYTE *)(v10 + 4) & 5) == 0 )
      {
        if ( (*(_DWORD *)v10 & 0xFFFFFFFD) == 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, *(_QWORD *)(v10 + 8));
          if ( (v11 & 0x1FFF0000) == 0x70000 )
            v11 = (unsigned __int16)v11;
          if ( v11 )
          {
LABEL_17:
            *(_DWORD *)(v10 + 4) = 2;
            v4 = v11;
            continue;
          }
          if ( !v6 && *(_BYTE *)(*(_QWORD *)(v10 + 8) + 1LL) == 52 )
          {
            v12 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"REQUEST");
            if ( v12 )
            {
              CertCloseStore(v12, 0);
              v6 = 1;
            }
          }
          goto LABEL_9;
        }
        if ( *(_DWORD *)v10 == 4 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, *(_QWORD *)(v10 + 8));
          if ( (v11 & 0x1FFF0000) == 0x70000 )
            v11 = (unsigned __int16)v11;
          if ( v11 )
            goto LABEL_17;
LABEL_9:
          *(_DWORD *)(v10 + 4) = 1;
        }
      }
    }
    if ( v3 == *a3 )
      return v4;
    v3 = *a3;
    v5 = *((_DWORD *)a3 + 2);
  }
}

```

## disassembly

```asm
0x1800052f8  mov     [rsp+arg_18], rbx
0x1800052fd  push    rbp
0x1800052fe  push    rsi
0x1800052ff  push    rdi
0x180005300  push    r12
0x180005302  push    r13
0x180005304  push    r14
0x180005306  push    r15
0x180005308  sub     rsp, 30h
0x18000530c  mov     r14, [rdx]
0x18000530f  xor     ebp, ebp
0x180005311  mov     esi, [rdx+8]
0x180005314  xor     r12d, r12d
0x180005317  mov     r15, r8
0x18000531a  mov     r13, rcx
0x18000531d  xor     edi, edi
0x18000531f  test    esi, esi
0x180005321  jz      loc_1800053FB
0x180005327  mov     rbx, [r14+rdi*8]
0x18000532b  test    byte ptr [rbx+4], 5
0x18000532f  jnz     loc_1800053F1
0x180005335  test    dword ptr [rbx], 0FFFFFFFDh
0x18000533b  jz      short loc_180005378
0x18000533d  cmp     dword ptr [rbx], 4
0x180005340  jnz     loc_1800053F1
0x180005346  mov     rax, [r13+0]
0x18000534a  mov     rcx, r13
0x18000534d  mov     rdx, [rbx+8]
0x180005351  mov     rax, [rax+20h]
0x180005355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535a  mov     ecx, eax
0x18000535c  and     eax, 1FFF0000h
0x180005361  cmp     eax, 70000h
0x180005366  jnz     short loc_18000536B
0x180005368  movzx   ecx, cx
0x18000536b  test    ecx, ecx
0x18000536d  jnz     short loc_1800053E8
0x18000536f  mov     dword ptr [rbx+4], 1
0x180005376  jmp     short loc_1800053F1
0x180005378  mov     rax, [r13+0]
0x18000537c  mov     rcx, r13
0x18000537f  mov     rdx, [rbx+8]
0x180005383  mov     rax, [rax+18h]
0x180005387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538c  mov     ecx, eax
0x18000538e  and     eax, 1FFF0000h
0x180005393  cmp     eax, 70000h
0x180005398  jnz     short loc_18000539D
0x18000539a  movzx   ecx, cx
0x18000539d  test    ecx, ecx
0x18000539f  jnz     short loc_1800053E8
0x1800053a1  test    r12d, r12d
0x1800053a4  jnz     short loc_18000536F
0x1800053a6  mov     rax, [rbx+8]
0x1800053aa  cmp     byte ptr [rax+1], 34h ; '4'
0x1800053ae  jnz     short loc_18000536F
0x1800053b0  xor     edx, edx; dwEncodingType
0x1800053b2  lea     rax, aRequest; "REQUEST"
0x1800053b9  mov     r9d, 10000h; dwFlags
0x1800053bf  mov     [rsp+68h+pvPara], rax; pvPara
0x1800053c4  xor     r8d, r8d; hCryptProv
0x1800053c7  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800053ca  call    cs:__imp_CertOpenStore
0x1800053d0  test    rax, rax
0x1800053d3  jz      short loc_18000536F
0x1800053d5  xor     edx, edx; dwFlags
0x1800053d7  mov     rcx, rax; hCertStore
0x1800053da  call    cs:__imp_CertCloseStore
0x1800053e0  mov     r12d, 1
0x1800053e6  jmp     short loc_18000536F
0x1800053e8  mov     dword ptr [rbx+4], 2
0x1800053ef  mov     ebp, ecx
0x1800053f1  inc     edi
0x1800053f3  cmp     edi, esi
0x1800053f5  jb      loc_180005327
0x1800053fb  cmp     r14, [r15]
0x1800053fe  jz      short loc_18000540C
0x180005400  mov     r14, [r15]
0x180005403  mov     esi, [r15+8]
0x180005407  jmp     loc_18000531D
0x18000540c  mov     rbx, [rsp+68h+arg_18]
0x180005414  mov     eax, ebp
0x180005416  add     rsp, 30h
0x18000541a  pop     r15
0x18000541c  pop     r14
0x18000541e  pop     r13
0x180005420  pop     r12
0x180005422  pop     rdi
0x180005423  pop     rsi
0x180005424  pop     rbp
0x180005425  retn
```
