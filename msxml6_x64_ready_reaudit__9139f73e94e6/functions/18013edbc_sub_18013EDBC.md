# sub_18013EDBC

- ea: `0x18013edbc`
- end: `0x18013eee0`
- name: `sub_18013EDBC`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18013e140`

## callees

- `0x18013edbc`
- `0x180140e3c`
- `0x180189008`
- `0x180189e3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013ee52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013ee52`

## pseudocode

```c
__int64 __fastcall sub_18013EDBC(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // r10d
  int v11; // ebx
  int v12; // ebx
  int v13; // r8d
  __int64 v14; // rcx
  int v16; // [rsp+A0h] [rbp+18h] BYREF

  v16 = 0;
  if ( (xmmword_1801FAD20 & 2) != 0 )
  {
    if ( a2 )
    {
      v6 = *(_QWORD *)a2;
      v7 = *(_QWORD *)(a2 + 8);
      v8 = *(_QWORD *)(a2 + 16);
      v9 = *(_QWORD *)(a2 + 24);
      v10 = *(_DWORD *)(a2 + 40);
    }
    else
    {
      v6 = 0;
      v7 = 0;
      v8 = 0;
      v9 = 0;
      LOBYTE(v10) = 0;
    }
    sub_180189E3C(v7, 143, v8, a1, a2, v6, v7, v8, v9, v10, (char)a3);
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( !*(_DWORD *)(a1 + 48) || (v12 = *(_DWORD *)(a1 + 48), v12 == GetCurrentThreadId()) )
    {
      v11 = sub_180140E3C(*(_QWORD *)(a1 + 40), a2, &v16);
      if ( v11 >= 0 )
        *a3 = v16;
    }
    else
    {
      v11 = -2147417842;
    }
  }
  else
  {
    v11 = -2147467261;
  }
  v13 = v11 >> 31;
  if ( (xmmword_1801FAD00[(v11 >> 31) + 2] & 2) != 0 )
  {
    v14 = (unsigned __int16)(v13 + 2) << 9;
    LOWORD(v14) = (((_WORD)v13 + 2) << 9) | 1;
    sub_180189008(v14, 144, qword_1801DA730, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18013edbc  mov     rax, rsp
0x18013edbf  push    rbx
0x18013edc0  push    rbp
0x18013edc1  push    rsi
0x18013edc2  push    rdi
0x18013edc3  sub     rsp, 68h
0x18013edc7  mov     rsi, r8
0x18013edca  mov     dword ptr [rax+18h], 0
0x18013edd1  mov     rdi, rdx
0x18013edd4  mov     rbp, rcx
0x18013edd7  test    byte ptr cs:xmmword_1801FAD20, 2
0x18013edde  jz      short loc_18013EE37
0x18013ede0  test    rdx, rdx
0x18013ede3  jz      short loc_18013EDFA
0x18013ede5  mov     rax, [rdx]
0x18013ede8  mov     rcx, [rdx+8]
0x18013edec  mov     r8, [rdx+10h]
0x18013edf0  mov     r9, [rdx+18h]
0x18013edf4  mov     r10d, [rdx+28h]
0x18013edf8  jmp     short loc_18013EE07
0x18013edfa  xor     eax, eax
0x18013edfc  xor     ecx, ecx
0x18013edfe  xor     r8d, r8d
0x18013ee01  xor     r9d, r9d
0x18013ee04  xor     r10d, r10d
0x18013ee07  mov     [rsp+88h+var_38], rsi
0x18013ee0c  mov     edx, 8Fh
0x18013ee11  mov     [rsp+88h+var_40], r10d
0x18013ee16  mov     [rsp+88h+var_48], r9
0x18013ee1b  mov     r9, rbp
0x18013ee1e  mov     [rsp+88h+var_50], r8
0x18013ee23  mov     [rsp+88h+var_58], rcx
0x18013ee28  mov     [rsp+88h+var_60], rax
0x18013ee2d  mov     [rsp+88h+var_68], rdi
0x18013ee32  call    sub_180189E3C
0x18013ee37  test    rsi, rsi
0x18013ee3a  jnz     short loc_18013EE43
0x18013ee3c  mov     ebx, 80004003h
0x18013ee41  jmp     short loc_18013EE8C
0x18013ee43  mov     dword ptr [rsi], 0
0x18013ee49  cmp     dword ptr [rbp+30h], 0
0x18013ee4d  jz      short loc_18013EE69
0x18013ee4f  mov     ebx, [rbp+30h]
0x18013ee52  call    cs:GetCurrentThreadId
0x18013ee59  nop     dword ptr [rax+rax+00h]
0x18013ee5e  cmp     ebx, eax
0x18013ee60  jz      short loc_18013EE69
0x18013ee62  mov     ebx, 8001010Eh
0x18013ee67  jmp     short loc_18013EE8C
0x18013ee69  mov     rcx, [rbp+28h]
0x18013ee6d  lea     r8, [rsp+88h+arg_10]
0x18013ee75  mov     rdx, rdi
0x18013ee78  call    sub_180140E3C
0x18013ee7d  mov     ebx, eax
0x18013ee7f  test    eax, eax
0x18013ee81  js      short loc_18013EE8C
0x18013ee83  mov     ecx, [rsp+88h+arg_10]
0x18013ee8a  mov     [rsi], ecx
0x18013ee8c  mov     r8d, ebx
0x18013ee8f  lea     rax, xmmword_1801FAD00
0x18013ee96  sar     r8d, 1Fh
0x18013ee9a  lea     ecx, ds:4[r8*2]
0x18013eea2  movsxd  rdx, ecx
0x18013eea5  test    byte ptr [rax+rdx*8], 2
0x18013eea9  jz      short loc_18013EED4
0x18013eeab  add     r8w, 2
0x18013eeb0  mov     eax, 200h
0x18013eeb5  movzx   ecx, r8w
0x18013eeb9  mov     edx, 90h
0x18013eebe  imul    ecx, eax
0x18013eec1  lea     r8, qword_1801DA730
0x18013eec8  mov     r9d, ebx
0x18013eecb  or      cx, 1
0x18013eecf  call    sub_180189008
0x18013eed4  mov     eax, ebx
0x18013eed6  add     rsp, 68h
0x18013eeda  pop     rdi
0x18013eedb  pop     rsi
0x18013eedc  pop     rbp
0x18013eedd  pop     rbx
0x18013eede  retn
```
