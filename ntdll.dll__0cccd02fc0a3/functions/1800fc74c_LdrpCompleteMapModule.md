# LdrpCompleteMapModule

- ea: `0x1800fc74c`
- end: `0x1800fca1b`
- name: `LdrpCompleteMapModule`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029c3c`

## callees

- `0x18001eb80`
- `0x18004cef8`
- `0x1800526f0`
- `0x180066020`
- `0x1800acb14`
- `0x1800d0504`
- `0x1800fc74c`
- `0x1800fca24`
- `0x1800fe050`

## string_xrefs

- `0x1800fc94c`: `Could not validate the crypto signature for DLL %wZ\n`
- `0x1800fc945`: `LdrpCompleteMapModule`

## pseudocode

```c
__int64 __fastcall LdrpCompleteMapModule(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rbx
  __int64 v5; // r12
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rbp
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  char v26; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v5 = a2;
  v7 = 0;
  LOBYTE(a2) = 1;
  v9 = RtlImageDirectoryEntryToData(*(_QWORD *)(v3 + 48), a2, 14, &v26);
  if ( !v9 )
    goto LABEL_6;
  if ( (*(_DWORD *)(a1 + 32) & 0x800000) != 0 )
    return (unsigned int)-1073741701;
  *(_DWORD *)(v3 + 104) |= 0x400000u;
  if ( (*(_BYTE *)(v9 + 16) & 1) == 0
    || (*(_DWORD *)(v3 + 104) |= 0x1000000u, v7 = LdrpCorValidateImage(*(_QWORD *)(v3 + 48)), v7 >= 0)
    && ((*(_DWORD *)(a1 + 32) & 0x200000) == 0 || (v7 = LdrpCorFixupImage(*(_QWORD *)(v3 + 48)), v7 >= 0)) )
  {
LABEL_6:
    if ( (*(_WORD *)(v5 + 22) & 0x2000) != 0 )
    {
      if ( *(char *)(a1 + 32) >= 0 || *(char *)(v5 + 94) < 0 )
      {
        if ( (*(_DWORD *)(v3 + 104) & 0x1000000) == 0 && (a3 == 1073741827 || a3 == 1073741878) )
        {
          v16 = 2147353476;
          if ( (unsigned int)RtlGetCurrentServiceSessionId((unsigned int)(a3 - 1073741827), v8, v10, v11) )
            v17 = (__int64)NtCurrentPeb()->SharedData + 554;
          else
            v17 = 2147353476;
          v18 = 2147353477;
          if ( *(_BYTE *)v17 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
          {
            v17 = (unsigned int)RtlGetCurrentServiceSessionId(v17, v13, v14, v15)
                ? (__int64)NtCurrentPeb()->SharedData + 555
                : 2147353477LL;
            if ( (*(_BYTE *)v17 & 0x20) != 0 )
            {
              LOBYTE(v15) = -1;
              LOBYTE(v14) = -1;
              LdrpLogEtwEvent(5264, *(_QWORD *)(v3 + 48), v14, v15, 0, 0);
            }
          }
          if ( a3 == 1073741827 && (v25 = LdrpRelocateImage(*(_QWORD *)(v3 + 48)), v7 = v25, v25 < 0) )
          {
            LdrpLogError((unsigned int)v25, 5264, 0, v3 + 72);
          }
          else
          {
            if ( (unsigned int)RtlGetCurrentServiceSessionId(v17, v13, v14, v15) )
              v16 = (__int64)NtCurrentPeb()->SharedData + 554;
            if ( *(_BYTE *)v16 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
            {
              if ( (unsigned int)RtlGetCurrentServiceSessionId(v20, v19, v21, v22) )
                v18 = (__int64)NtCurrentPeb()->SharedData + 555;
              if ( (*(_BYTE *)v18 & 0x20) != 0 )
              {
                LOBYTE(v24) = -1;
                LOBYTE(v23) = -1;
                LdrpLogEtwEvent(5265, *(_QWORD *)(v3 + 48), v23, v24, 0, 0);
              }
            }
          }
        }
      }
      else
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrmap.c",
          1107,
          (int)"LdrpCompleteMapModule",
          0,
          "Could not validate the crypto signature for DLL %wZ\n",
          v3 + 72);
        return (unsigned int)-1073740760;
      }
    }
    else
    {
      *(_DWORD *)(v3 + 104) &= ~4u;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800fc74c  mov     [rsp+arg_8], rbx
0x1800fc751  mov     [rsp+arg_10], rbp
0x1800fc756  push    rsi
0x1800fc757  push    rdi
0x1800fc758  push    r12
0x1800fc75a  push    r14
0x1800fc75c  push    r15
0x1800fc75e  sub     rsp, 30h
0x1800fc762  mov     rbx, [rcx+38h]
0x1800fc766  lea     r9, [rsp+58h+arg_0]
0x1800fc76b  mov     r14d, r8d
0x1800fc76e  mov     r12, rdx
0x1800fc771  mov     r15, rcx
0x1800fc774  xor     edi, edi
0x1800fc776  mov     dl, 1
0x1800fc778  mov     rcx, [rbx+30h]
0x1800fc77c  lea     r8d, [rdi+0Eh]
0x1800fc780  call    RtlImageDirectoryEntryToData
0x1800fc785  mov     rcx, rax
0x1800fc788  mov     esi, 1000000h
0x1800fc78d  test    rax, rax
0x1800fc790  jz      short loc_1800FC7CF
0x1800fc792  test    dword ptr [r15+20h], 800000h
0x1800fc79a  jz      short loc_1800FC7BB
0x1800fc79c  mov     edi, 0C000007Bh
0x1800fc7a1  mov     rbx, [rsp+58h+arg_8]
0x1800fc7a6  mov     eax, edi
0x1800fc7a8  mov     rbp, [rsp+58h+arg_10]
0x1800fc7ad  add     rsp, 30h
0x1800fc7b1  pop     r15
0x1800fc7b3  pop     r14
0x1800fc7b5  pop     r12
0x1800fc7b7  pop     rdi
0x1800fc7b8  pop     rsi
0x1800fc7b9  retn
0x1800fc7bb  mov     eax, [rbx+68h]
0x1800fc7be  bts     eax, 16h
0x1800fc7c2  mov     [rbx+68h], eax
0x1800fc7c5  test    byte ptr [rcx+10h], 1
0x1800fc7c9  jnz     loc_1800FC8EC
0x1800fc7cf  mov     eax, 2000h
0x1800fc7d4  test    [r12+16h], ax
0x1800fc7da  jz      loc_1800FC9D4
0x1800fc7e0  test    byte ptr [r15+20h], 80h
0x1800fc7e5  jnz     loc_1800FC92D
0x1800fc7eb  mov     eax, [rbx+68h]
0x1800fc7ee  test    esi, eax
0x1800fc7f0  jnz     short loc_1800FC7A1
0x1800fc7f2  mov     ecx, r14d
0x1800fc7f5  sub     ecx, 40000003h
0x1800fc7fb  jz      short loc_1800FC802
0x1800fc7fd  cmp     ecx, 33h ; '3'
0x1800fc800  jnz     short loc_1800FC7A1
0x1800fc802  call    RtlGetCurrentServiceSessionId
0x1800fc807  mov     esi, 7FFE0384h
0x1800fc80c  test    eax, eax
0x1800fc80e  jz      loc_1800FC973
0x1800fc814  mov     rax, gs:60h
0x1800fc81d  mov     rcx, [rax+90h]
0x1800fc824  add     rcx, 22Ah
0x1800fc82b  cmp     byte ptr [rcx], 0
0x1800fc82e  mov     ebp, 7FFE0385h
0x1800fc833  jz      short loc_1800FC84B
0x1800fc835  mov     rax, gs:60h
0x1800fc83e  test    byte ptr [rax+378h], 4
0x1800fc845  jnz     loc_1800FC97B
0x1800fc84b  cmp     r14d, 40000003h
0x1800fc852  jz      loc_1800FC9E2
0x1800fc858  call    RtlGetCurrentServiceSessionId
0x1800fc85d  test    eax, eax
0x1800fc85f  jz      short loc_1800FC878
0x1800fc861  mov     rax, gs:60h
0x1800fc86a  mov     rsi, [rax+90h]
0x1800fc871  add     rsi, 22Ah
0x1800fc878  cmp     byte ptr [rsi], 0
0x1800fc87b  jz      loc_1800FC7A1
0x1800fc881  mov     rax, gs:60h
0x1800fc88a  test    byte ptr [rax+378h], 4
0x1800fc891  jz      loc_1800FC7A1
0x1800fc897  call    RtlGetCurrentServiceSessionId
0x1800fc89c  test    eax, eax
0x1800fc89e  jz      short loc_1800FC8B7
0x1800fc8a0  mov     rax, gs:60h
0x1800fc8a9  mov     rbp, [rax+90h]
0x1800fc8b0  add     rbp, 22Bh
0x1800fc8b7  test    byte ptr [rbp+0], 20h
0x1800fc8bb  jz      loc_1800FC7A1
0x1800fc8c1  mov     rdx, [rbx+30h]
0x1800fc8c5  mov     r9b, 0FFh
0x1800fc8c8  mov     r8b, r9b
0x1800fc8cb  mov     qword ptr [rsp+58h+ArgList], 0
0x1800fc8d4  mov     ecx, 1491h
0x1800fc8d9  mov     [rsp+58h+Format], 0
0x1800fc8e2  call    LdrpLogEtwEvent
0x1800fc8e7  jmp     loc_1800FC7A1
0x1800fc8ec  mov     eax, [rbx+68h]
0x1800fc8ef  or      eax, esi
0x1800fc8f1  mov     [rbx+68h], eax
0x1800fc8f4  mov     rcx, [rbx+30h]
0x1800fc8f8  call    LdrpCorValidateImage
0x1800fc8fd  mov     edi, eax
0x1800fc8ff  test    eax, eax
0x1800fc901  js      loc_1800FC7A1
0x1800fc907  test    dword ptr [r15+20h], 200000h
0x1800fc90f  jz      loc_1800FC7CF
0x1800fc915  mov     rcx, [rbx+30h]
0x1800fc919  call    LdrpCorFixupImage
0x1800fc91e  mov     edi, eax
0x1800fc920  test    eax, eax
0x1800fc922  js      loc_1800FC7A1
0x1800fc928  jmp     loc_1800FC7CF
0x1800fc92d  test    byte ptr [r12+5Eh], 80h
0x1800fc933  jnz     loc_1800FC7EB
0x1800fc939  lea     rax, [rbx+48h]
0x1800fc93d  xor     r9d, r9d; int
0x1800fc940  mov     qword ptr [rsp+58h+ArgList], rax; ArgList
0x1800fc945  lea     r8, aLdrpcompletema; "LdrpCompleteMapModule"
0x1800fc94c  lea     rax, aCouldNotValida; "Could not validate the crypto signature"...
0x1800fc953  mov     edx, 453h; int
0x1800fc958  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800fc95f  mov     [rsp+58h+Format], rax; Format
0x1800fc964  call    LdrpLogInternal
0x1800fc969  mov     edi, 0C0000428h
0x1800fc96e  jmp     loc_1800FC7A1
0x1800fc973  mov     rcx, rsi
0x1800fc976  jmp     loc_1800FC82B
0x1800fc97b  call    RtlGetCurrentServiceSessionId
0x1800fc980  test    eax, eax
0x1800fc982  jz      short loc_1800FC9CF
0x1800fc984  mov     rax, gs:60h
0x1800fc98d  mov     rcx, [rax+90h]
0x1800fc994  add     rcx, 22Bh
0x1800fc99b  test    byte ptr [rcx], 20h
0x1800fc99e  jz      loc_1800FC84B
0x1800fc9a4  mov     rdx, [rbx+30h]
0x1800fc9a8  mov     r9b, 0FFh
0x1800fc9ab  mov     r8b, r9b
0x1800fc9ae  mov     qword ptr [rsp+58h+ArgList], 0
0x1800fc9b7  mov     ecx, 1490h
0x1800fc9bc  mov     [rsp+58h+Format], 0
0x1800fc9c5  call    LdrpLogEtwEvent
0x1800fc9ca  jmp     loc_1800FC84B
0x1800fc9cf  mov     rcx, rbp
0x1800fc9d2  jmp     short loc_1800FC99B
0x1800fc9d4  mov     eax, [rbx+68h]
0x1800fc9d7  and     eax, 0FFFFFFFBh
0x1800fc9da  mov     [rbx+68h], eax
0x1800fc9dd  jmp     loc_1800FC7A1
0x1800fc9e2  mov     rdx, [r15+0A8h]
0x1800fc9e9  lea     r9, [rbx+48h]
0x1800fc9ed  mov     rcx, [rbx+30h]
0x1800fc9f1  mov     r8, r12
0x1800fc9f4  call    LdrpRelocateImage
0x1800fc9f9  mov     edi, eax
0x1800fc9fb  test    eax, eax
0x1800fc9fd  jns     loc_1800FC858
0x1800fca03  mov     edx, 1490h
0x1800fca08  lea     r9, [rbx+48h]
0x1800fca0c  xor     r8d, r8d
0x1800fca0f  mov     ecx, eax
0x1800fca11  call    LdrpLogError
0x1800fca16  jmp     loc_1800FC7A1
```
