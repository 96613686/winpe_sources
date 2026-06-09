# FIPfOpenListNotifyConflictStart

- ea: `0x140017e44`
- end: `0x140017fc1`
- name: `FIPfOpenListNotifyConflictStart`
- size: `381`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140015a48`
- `0x14001606c`

## callees

- `0x140003a00`
- `0x140017e44`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140017f68`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140017f68`
- `ntoskrnl!ExAllocatePool2` at `0x140017eef`
- `ntoskrnl!ExAllocatePool2` at `0x140017eef`

## pseudocode

```c
__int64 __fastcall FIPfOpenListNotifyConflictStart(_QWORD *a1, __int64 a2, int a3, __int64 a4)
{
  _QWORD *v6; // rsi
  unsigned int v7; // ebp
  __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // rcx
  int v12; // eax
  __int64 Pool2; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned __int64 v16; // r10
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rax
  __int128 v20; // [rsp+20h] [rbp-38h] BYREF

  v20 = 0;
  _InterlockedIncrement(&dword_14000981C[a3]);
  v6 = (_QWORD *)*a1;
  v7 = 0;
  while ( v6 != a1 )
  {
    v8 = v6[5];
    v9 = *(_QWORD *)a4;
    v10 = *(_QWORD *)(v8 + 8);
    if ( (*(_BYTE *)(a4 + 8) & 1) != 0 && v9 )
      v9 ^= a4;
    if ( !v9 )
      goto LABEL_16;
    do
    {
      if ( *(_QWORD *)(v9 + 24) > v10 )
      {
        v11 = *(_QWORD *)v9;
      }
      else
      {
        if ( *(_QWORD *)(v9 + 24) >= v10 )
          break;
        v11 = *(_QWORD *)(v9 + 8);
      }
      if ( (*(_BYTE *)(a4 + 8) & 1) != 0 && v11 )
        v9 ^= v11;
      else
        v9 = v11;
    }
    while ( v9 );
    if ( !v9 )
    {
LABEL_16:
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))v8)(*(_QWORD *)(v8 + 8), 0, &v20);
      if ( v12 < 0 )
        v7 = v12;
      Pool2 = ExAllocatePool2(64, 48, 1666074950);
      v15 = Pool2;
      if ( Pool2 )
      {
        *(_OWORD *)Pool2 = 0;
        *(_OWORD *)(Pool2 + 16) = 0;
        *(_OWORD *)(Pool2 + 32) = 0;
        v16 = *(_QWORD *)(v8 + 8);
        *(_QWORD *)(Pool2 + 24) = v16;
        *(_OWORD *)(Pool2 + 32) = v20;
        v17 = *(_QWORD *)a4;
        if ( (*(_BYTE *)(a4 + 8) & 1) != 0 && v17 )
          v17 ^= a4;
        LOBYTE(v14) = 0;
        if ( v17 )
        {
          while ( 1 )
          {
            if ( *(_QWORD *)(v17 + 24) > v16 )
            {
              v18 = *(_QWORD *)v17;
              if ( (*(_BYTE *)(a4 + 8) & 1) != 0 )
              {
                if ( !v18 )
                  break;
                v18 ^= v17;
              }
              if ( !v18 )
                break;
            }
            else
            {
              v18 = *(_QWORD *)(v17 + 8);
              if ( (*(_BYTE *)(a4 + 8) & 1) != 0 )
              {
                if ( !v18 )
                  goto LABEL_28;
                v18 ^= v17;
              }
              if ( !v18 )
              {
LABEL_28:
                LOBYTE(v14) = 1;
                break;
              }
            }
            v17 = v18;
          }
        }
        RtlRbInsertNodeEx(a4, v17, v14, v15);
      }
      else
      {
        ((void (__fastcall *)(_QWORD, _QWORD))v20)(*(_QWORD *)(v8 + 8), *((_QWORD *)&v20 + 1));
        v7 = -1073741670;
      }
    }
    v6 = (_QWORD *)*v6;
  }
  return v7;
}

```

## disassembly

```asm
0x140017e44  push    rbx
0x140017e46  push    rbp
0x140017e47  push    rsi
0x140017e48  push    rdi
0x140017e49  push    r14
0x140017e4b  sub     rsp, 30h
0x140017e4f  xorps   xmm0, xmm0
0x140017e52  movsxd  rax, r8d
0x140017e55  mov     r14, rcx
0x140017e58  mov     rbx, r9
0x140017e5b  movups  [rsp+58h+var_38], xmm0
0x140017e60  lea     rcx, dword_14000981C
0x140017e67  lock inc dword ptr [rcx+rax*4]
0x140017e6b  mov     rsi, [r14]
0x140017e6e  xor     ebp, ebp
0x140017e70  jmp     loc_140017FAA
0x140017e75  test    byte ptr [rbx+8], 1
0x140017e79  mov     rdi, [rsi+28h]
0x140017e7d  mov     rax, [rbx]
0x140017e80  mov     r9, [rdi+8]
0x140017e84  jz      short loc_140017E8E
0x140017e86  test    rax, rax
0x140017e89  jz      short loc_140017E8E
0x140017e8b  xor     rax, rbx
0x140017e8e  movzx   edx, byte ptr [rbx+8]
0x140017e92  and     edx, 1
0x140017e95  test    rax, rax
0x140017e98  jz      short loc_140017ECA
0x140017e9a  cmp     [rax+18h], r9
0x140017e9e  ja      short loc_140017EA8
0x140017ea0  jnb     short loc_140017EC1
0x140017ea2  mov     rcx, [rax+8]
0x140017ea6  jmp     short loc_140017EAB
0x140017ea8  mov     rcx, [rax]
0x140017eab  test    edx, edx
0x140017ead  jz      short loc_140017EB9
0x140017eaf  test    rcx, rcx
0x140017eb2  jz      short loc_140017EB9
0x140017eb4  xor     rax, rcx
0x140017eb7  jmp     short loc_140017EBC
0x140017eb9  mov     rax, rcx
0x140017ebc  test    rax, rax
0x140017ebf  jnz     short loc_140017E9A
0x140017ec1  test    rax, rax
0x140017ec4  jnz     loc_140017FA7
0x140017eca  mov     rax, [rdi]
0x140017ecd  lea     r8, [rsp+58h+var_38]
0x140017ed2  xor     edx, edx
0x140017ed4  mov     rcx, r9
0x140017ed7  call    _guard_dispatch_icall
0x140017edc  mov     edx, 30h ; '0'
0x140017ee1  test    eax, eax
0x140017ee3  mov     r8d, 634E4946h
0x140017ee9  cmovs   ebp, eax
0x140017eec  lea     ecx, [rdx+10h]
0x140017eef  call    cs:__imp_ExAllocatePool2
0x140017ef6  nop     dword ptr [rax+rax+00h]
0x140017efb  mov     r9, rax
0x140017efe  test    rax, rax
0x140017f01  jz      loc_140017F8F
0x140017f07  xorps   xmm0, xmm0
0x140017f0a  movups  xmmword ptr [rax], xmm0
0x140017f0d  movups  xmmword ptr [rax+10h], xmm0
0x140017f11  movups  xmmword ptr [rax+20h], xmm0
0x140017f15  mov     r10, [rdi+8]
0x140017f19  mov     [rax+18h], r10
0x140017f1d  movups  xmm0, [rsp+58h+var_38]
0x140017f22  movdqu  xmmword ptr [rax+20h], xmm0
0x140017f27  test    byte ptr [rbx+8], 1
0x140017f2b  mov     rdx, [rbx]
0x140017f2e  jz      short loc_140017F38
0x140017f30  test    rdx, rdx
0x140017f33  jz      short loc_140017F38
0x140017f35  xor     rdx, rbx
0x140017f38  movzx   ecx, byte ptr [rbx+8]
0x140017f3c  xor     r8b, r8b
0x140017f3f  and     ecx, 1
0x140017f42  test    rdx, rdx
0x140017f45  jz      short loc_140017F65
0x140017f47  cmp     [rdx+18h], r10
0x140017f4b  ja      short loc_140017F76
0x140017f4d  mov     rax, [rdx+8]
0x140017f51  test    ecx, ecx
0x140017f53  jz      short loc_140017F5D
0x140017f55  test    rax, rax
0x140017f58  jz      short loc_140017F62
0x140017f5a  xor     rax, rdx
0x140017f5d  test    rax, rax
0x140017f60  jnz     short loc_140017F8A
0x140017f62  mov     r8b, 1
0x140017f65  mov     rcx, rbx
0x140017f68  call    cs:__imp_RtlRbInsertNodeEx
0x140017f6f  nop     dword ptr [rax+rax+00h]
0x140017f74  jmp     short loc_140017FA7
0x140017f76  mov     rax, [rdx]
0x140017f79  test    ecx, ecx
0x140017f7b  jz      short loc_140017F85
0x140017f7d  test    rax, rax
0x140017f80  jz      short loc_140017F65
0x140017f82  xor     rax, rdx
0x140017f85  test    rax, rax
0x140017f88  jz      short loc_140017F65
0x140017f8a  mov     rdx, rax
0x140017f8d  jmp     short loc_140017F47
0x140017f8f  mov     rdx, qword ptr [rsp+58h+var_38+8]
0x140017f94  mov     rcx, [rdi+8]
0x140017f98  mov     rax, qword ptr [rsp+58h+var_38]
0x140017f9d  call    _guard_dispatch_icall
0x140017fa2  mov     ebp, 0C000009Ah
0x140017fa7  mov     rsi, [rsi]
0x140017faa  cmp     rsi, r14
0x140017fad  jnz     loc_140017E75
0x140017fb3  mov     eax, ebp
0x140017fb5  add     rsp, 30h
0x140017fb9  pop     r14
0x140017fbb  pop     rdi
0x140017fbc  pop     rsi
0x140017fbd  pop     rbp
0x140017fbe  pop     rbx
0x140017fbf  retn
```
