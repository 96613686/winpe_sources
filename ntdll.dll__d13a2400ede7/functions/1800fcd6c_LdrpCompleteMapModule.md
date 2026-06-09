# LdrpCompleteMapModule

- ea: `0x1800fcd6c`
- end: `0x1800fd03b`
- name: `LdrpCompleteMapModule`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029b2c`

## callees

- `0x18001eb80`
- `0x180069af8`
- `0x18006f0d0`
- `0x180082a00`
- `0x1800b7654`
- `0x1800d1c34`
- `0x1800fcd6c`
- `0x1800fd044`
- `0x1800fe670`

## string_xrefs

- `0x1800fcf65`: `LdrpCompleteMapModule`
- `0x1800fcf6c`: `Could not validate the crypto signature for DLL %wZ\n`

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
0x1800fcd6c  mov     [rsp+arg_8], rbx
0x1800fcd71  mov     [rsp+arg_10], rbp
0x1800fcd76  push    rsi
0x1800fcd77  push    rdi
0x1800fcd78  push    r12
0x1800fcd7a  push    r14
0x1800fcd7c  push    r15
0x1800fcd7e  sub     rsp, 30h
0x1800fcd82  mov     rbx, [rcx+38h]
0x1800fcd86  lea     r9, [rsp+58h+arg_0]
0x1800fcd8b  mov     r14d, r8d
0x1800fcd8e  mov     r12, rdx
0x1800fcd91  mov     r15, rcx
0x1800fcd94  xor     edi, edi
0x1800fcd96  mov     dl, 1
0x1800fcd98  mov     rcx, [rbx+30h]
0x1800fcd9c  lea     r8d, [rdi+0Eh]
0x1800fcda0  call    RtlImageDirectoryEntryToData
0x1800fcda5  mov     rcx, rax
0x1800fcda8  mov     esi, 1000000h
0x1800fcdad  test    rax, rax
0x1800fcdb0  jz      short loc_1800FCDEF
0x1800fcdb2  test    dword ptr [r15+20h], 800000h
0x1800fcdba  jz      short loc_1800FCDDB
0x1800fcdbc  mov     edi, 0C000007Bh
0x1800fcdc1  mov     rbx, [rsp+58h+arg_8]
0x1800fcdc6  mov     eax, edi
0x1800fcdc8  mov     rbp, [rsp+58h+arg_10]
0x1800fcdcd  add     rsp, 30h
0x1800fcdd1  pop     r15
0x1800fcdd3  pop     r14
0x1800fcdd5  pop     r12
0x1800fcdd7  pop     rdi
0x1800fcdd8  pop     rsi
0x1800fcdd9  retn
0x1800fcddb  mov     eax, [rbx+68h]
0x1800fcdde  bts     eax, 16h
0x1800fcde2  mov     [rbx+68h], eax
0x1800fcde5  test    byte ptr [rcx+10h], 1
0x1800fcde9  jnz     loc_1800FCF0C
0x1800fcdef  mov     eax, 2000h
0x1800fcdf4  test    [r12+16h], ax
0x1800fcdfa  jz      loc_1800FCFF4
0x1800fce00  test    byte ptr [r15+20h], 80h
0x1800fce05  jnz     loc_1800FCF4D
0x1800fce0b  mov     eax, [rbx+68h]
0x1800fce0e  test    esi, eax
0x1800fce10  jnz     short loc_1800FCDC1
0x1800fce12  mov     ecx, r14d
0x1800fce15  sub     ecx, 40000003h
0x1800fce1b  jz      short loc_1800FCE22
0x1800fce1d  cmp     ecx, 33h ; '3'
0x1800fce20  jnz     short loc_1800FCDC1
0x1800fce22  call    RtlGetCurrentServiceSessionId
0x1800fce27  mov     esi, 7FFE0384h
0x1800fce2c  test    eax, eax
0x1800fce2e  jz      loc_1800FCF93
0x1800fce34  mov     rax, gs:60h
0x1800fce3d  mov     rcx, [rax+90h]
0x1800fce44  add     rcx, 22Ah
0x1800fce4b  cmp     byte ptr [rcx], 0
0x1800fce4e  mov     ebp, 7FFE0385h
0x1800fce53  jz      short loc_1800FCE6B
0x1800fce55  mov     rax, gs:60h
0x1800fce5e  test    byte ptr [rax+378h], 4
0x1800fce65  jnz     loc_1800FCF9B
0x1800fce6b  cmp     r14d, 40000003h
0x1800fce72  jz      loc_1800FD002
0x1800fce78  call    RtlGetCurrentServiceSessionId
0x1800fce7d  test    eax, eax
0x1800fce7f  jz      short loc_1800FCE98
0x1800fce81  mov     rax, gs:60h
0x1800fce8a  mov     rsi, [rax+90h]
0x1800fce91  add     rsi, 22Ah
0x1800fce98  cmp     byte ptr [rsi], 0
0x1800fce9b  jz      loc_1800FCDC1
0x1800fcea1  mov     rax, gs:60h
0x1800fceaa  test    byte ptr [rax+378h], 4
0x1800fceb1  jz      loc_1800FCDC1
0x1800fceb7  call    RtlGetCurrentServiceSessionId
0x1800fcebc  test    eax, eax
0x1800fcebe  jz      short loc_1800FCED7
0x1800fcec0  mov     rax, gs:60h
0x1800fcec9  mov     rbp, [rax+90h]
0x1800fced0  add     rbp, 22Bh
0x1800fced7  test    byte ptr [rbp+0], 20h
0x1800fcedb  jz      loc_1800FCDC1
0x1800fcee1  mov     rdx, [rbx+30h]
0x1800fcee5  mov     r9b, 0FFh
0x1800fcee8  mov     r8b, r9b
0x1800fceeb  mov     qword ptr [rsp+58h+ArgList], 0
0x1800fcef4  mov     ecx, 1491h
0x1800fcef9  mov     [rsp+58h+Format], 0
0x1800fcf02  call    LdrpLogEtwEvent
0x1800fcf07  jmp     loc_1800FCDC1
0x1800fcf0c  mov     eax, [rbx+68h]
0x1800fcf0f  or      eax, esi
0x1800fcf11  mov     [rbx+68h], eax
0x1800fcf14  mov     rcx, [rbx+30h]
0x1800fcf18  call    LdrpCorValidateImage
0x1800fcf1d  mov     edi, eax
0x1800fcf1f  test    eax, eax
0x1800fcf21  js      loc_1800FCDC1
0x1800fcf27  test    dword ptr [r15+20h], 200000h
0x1800fcf2f  jz      loc_1800FCDEF
0x1800fcf35  mov     rcx, [rbx+30h]
0x1800fcf39  call    LdrpCorFixupImage
0x1800fcf3e  mov     edi, eax
0x1800fcf40  test    eax, eax
0x1800fcf42  js      loc_1800FCDC1
0x1800fcf48  jmp     loc_1800FCDEF
0x1800fcf4d  test    byte ptr [r12+5Eh], 80h
0x1800fcf53  jnz     loc_1800FCE0B
0x1800fcf59  lea     rax, [rbx+48h]
0x1800fcf5d  xor     r9d, r9d; int
0x1800fcf60  mov     qword ptr [rsp+58h+ArgList], rax; ArgList
0x1800fcf65  lea     r8, aLdrpcompletema; "LdrpCompleteMapModule"
0x1800fcf6c  lea     rax, aCouldNotValida; "Could not validate the crypto signature"...
0x1800fcf73  mov     edx, 453h; int
0x1800fcf78  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800fcf7f  mov     [rsp+58h+Format], rax; Format
0x1800fcf84  call    LdrpLogInternal
0x1800fcf89  mov     edi, 0C0000428h
0x1800fcf8e  jmp     loc_1800FCDC1
0x1800fcf93  mov     rcx, rsi
0x1800fcf96  jmp     loc_1800FCE4B
0x1800fcf9b  call    RtlGetCurrentServiceSessionId
0x1800fcfa0  test    eax, eax
0x1800fcfa2  jz      short loc_1800FCFEF
0x1800fcfa4  mov     rax, gs:60h
0x1800fcfad  mov     rcx, [rax+90h]
0x1800fcfb4  add     rcx, 22Bh
0x1800fcfbb  test    byte ptr [rcx], 20h
0x1800fcfbe  jz      loc_1800FCE6B
0x1800fcfc4  mov     rdx, [rbx+30h]
0x1800fcfc8  mov     r9b, 0FFh
0x1800fcfcb  mov     r8b, r9b
0x1800fcfce  mov     qword ptr [rsp+58h+ArgList], 0
0x1800fcfd7  mov     ecx, 1490h
0x1800fcfdc  mov     [rsp+58h+Format], 0
0x1800fcfe5  call    LdrpLogEtwEvent
0x1800fcfea  jmp     loc_1800FCE6B
0x1800fcfef  mov     rcx, rbp
0x1800fcff2  jmp     short loc_1800FCFBB
0x1800fcff4  mov     eax, [rbx+68h]
0x1800fcff7  and     eax, 0FFFFFFFBh
0x1800fcffa  mov     [rbx+68h], eax
0x1800fcffd  jmp     loc_1800FCDC1
0x1800fd002  mov     rdx, [r15+0A8h]
0x1800fd009  lea     r9, [rbx+48h]
0x1800fd00d  mov     rcx, [rbx+30h]
0x1800fd011  mov     r8, r12
0x1800fd014  call    LdrpRelocateImage
0x1800fd019  mov     edi, eax
0x1800fd01b  test    eax, eax
0x1800fd01d  jns     loc_1800FCE78
0x1800fd023  mov     edx, 1490h
0x1800fd028  lea     r9, [rbx+48h]
0x1800fd02c  xor     r8d, r8d
0x1800fd02f  mov     ecx, eax
0x1800fd031  call    LdrpLogError
0x1800fd036  jmp     loc_1800FCDC1
```
