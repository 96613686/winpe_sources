# RasAuthAttributeDestroy

- ea: `0x18000abc0`
- end: `0x18000ad11`
- name: `RasAuthAttributeDestroy`
- size: `337`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a20`
- `0x180009c08`
- `0x180009dc0`
- `0x18000a4c0`
- `0x18000a900`
- `0x18000dcf0`
- `0x180011414`
- `0x180014bd8`
- `0x180016e2c`
- `0x180018c8c`
- `0x180019034`
- `0x1800192e0`
- `0x180019c3c`

## callees

- `0x18000abc0`
- `0x180014610`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac96`

## pseudocode

```c
HLOCAL __fastcall RasAuthAttributeDestroy(char *hMem)
{
  int v2; // ebx
  char *v3; // rsi
  int v4; // ecx
  int v5; // ecx
  void *v6; // rcx
  HLOCAL result; // rax

  if ( hMem )
  {
    v2 = 0;
    if ( *(_DWORD *)hMem )
    {
      while ( 1 )
      {
        v3 = &hMem[16 * v2];
        v4 = *(_DWORD *)v3;
        if ( *(_DWORD *)v3 == 8250 )
          goto LABEL_13;
        if ( v4 <= 8097 )
          break;
        if ( v4 <= 9002 )
        {
          if ( v4 != 9002 )
          {
            v5 = v4 - 8102;
            if ( v5 )
            {
              if ( (unsigned int)(v5 - 898) > 1 )
                goto LABEL_15;
            }
          }
          goto LABEL_13;
        }
        if ( (unsigned int)(v4 - 9003) <= 1 )
          goto LABEL_13;
LABEL_15:
        if ( !*(_DWORD *)&hMem[16 * ++v2] )
          return LocalFree(hMem);
      }
      if ( v4 != 8097 )
      {
        switch ( v4 )
        {
          case 1:
          case 2:
          case 3:
          case 11:
          case 18:
          case 19:
          case 20:
          case 22:
          case 24:
          case 25:
          case 26:
          case 30:
          case 31:
          case 32:
          case 33:
          case 34:
          case 35:
          case 36:
          case 44:
          case 50:
          case 60:
          case 63:
          case 66:
          case 67:
          case 77:
          case 78:
          case 79:
          case 80:
          case 96:
          case 97:
            goto LABEL_13;
          default:
            goto LABEL_15;
        }
        goto LABEL_15;
      }
LABEL_13:
      v6 = (void *)*((_QWORD *)v3 + 1);
      if ( v6 )
      {
        memset_0(v6, 0, *((unsigned int *)v3 + 1));
        LocalFree(*((HLOCAL *)v3 + 1));
      }
      goto LABEL_15;
    }
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000abc0  test    rcx, rcx
0x18000abc3  jz      locret_18000ACA6
0x18000abc9  push    rdi
0x18000abca  sub     rsp, 20h
0x18000abce  mov     [rsp+28h+arg_0], rbx
0x18000abd3  mov     rdi, rcx
0x18000abd6  xor     ebx, ebx
0x18000abd8  cmp     [rcx], ebx
0x18000abda  jz      loc_18000AC93
0x18000abe0  mov     [rsp+28h+arg_8], rbp
0x18000abe5  lea     rbp, __ImageBase
0x18000abec  mov     [rsp+28h+arg_10], rsi
0x18000abf1  mov     esi, ebx
0x18000abf3  shl     rsi, 4
0x18000abf7  add     rsi, rdi
0x18000abfa  mov     ecx, [rsi]
0x18000abfc  cmp     ecx, 203Ah
0x18000ac02  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac04  cmp     ecx, 1FA1h
0x18000ac0a  jg      short loc_18000AC2C
0x18000ac0c  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac0e  dec     ecx; switch 97 cases
0x18000ac10  cmp     ecx, 60h
0x18000ac13  ja      short def_18000AC2A; jumptable 000000018000AC2A default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000ac15  movsxd  rax, ecx
0x18000ac18  movzx   eax, ds:(byte_18000ACB0 - 180000000h)[rax+rbp]
0x18000ac20  mov     ecx, ss:(jpt_18000AC2A - 180000000h)[rbp+rax*4]
0x18000ac27  add     rcx, rbp
0x18000ac2a  jmp     rcx; switch jump
0x18000ac2c  cmp     ecx, 232Ah
0x18000ac32  jg      short loc_18000AC4D
0x18000ac34  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac36  sub     ecx, 1FA6h
0x18000ac3c  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac3e  sub     ecx, 382h
0x18000ac44  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac46  cmp     ecx, 1
0x18000ac49  jnz     short def_18000AC2A; jumptable 000000018000AC2A default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000ac4b  jmp     short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac4d  sub     ecx, 232Bh
0x18000ac53  jz      short loc_18000AC5A; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac55  cmp     ecx, 1
0x18000ac58  jnz     short def_18000AC2A; jumptable 000000018000AC2A default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000ac5a  mov     rcx, [rsi+8]; jumptable 000000018000AC2A cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000ac5e  test    rcx, rcx
0x18000ac61  jz      short def_18000AC2A; jumptable 000000018000AC2A default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000ac63  mov     r8d, [rsi+4]; Size
0x18000ac67  xor     edx, edx; Val
0x18000ac69  call    memset_0
0x18000ac6e  mov     rcx, [rsi+8]; hMem
0x18000ac72  call    cs:__imp_LocalFree
0x18000ac78  inc     ebx; jumptable 000000018000AC2A default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000ac7a  mov     eax, ebx
0x18000ac7c  add     rax, rax
0x18000ac7f  cmp     dword ptr [rdi+rax*8], 0
0x18000ac83  jnz     loc_18000ABF1
0x18000ac89  mov     rsi, [rsp+28h+arg_10]
0x18000ac8e  mov     rbp, [rsp+28h+arg_8]
0x18000ac93  mov     rcx, rdi; hMem
0x18000ac96  call    cs:__imp_LocalFree
0x18000ac9c  mov     rbx, [rsp+28h+arg_0]
0x18000aca1  add     rsp, 20h
0x18000aca5  pop     rdi
0x18000aca6  retn
```
