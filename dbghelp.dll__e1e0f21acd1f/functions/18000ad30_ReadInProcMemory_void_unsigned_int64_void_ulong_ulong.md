# ReadInProcMemory(void *,unsigned __int64,void *,ulong,ulong *)

- ea: `0x18000ad30`
- end: `0x18000aee5`
- name: `?ReadInProcMemory@@YAHPEAX_K0KPEAK@Z`
- size: `437`
- prototype: `int(void *, unsigned __int64, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c04`
- `0x1800098c8`

## callees

- `0x18000ad30`
- `0x18000aeec`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aeb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aeb1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ae42`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ae42`

## pseudocode

```c
__int64 __fastcall ReadInProcMemory(void *a1, char *a2, char *a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // r14d
  char *v6; // r12
  char *v7; // r15
  unsigned int v8; // ebx
  unsigned int *v9; // r13
  int v10; // edi
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v12; // rsi
  __int64 (__fastcall *v13)(_QWORD, __int64, _QWORD *, _QWORD); // rax
  unsigned int v14; // esi
  __int64 i; // r13
  unsigned int v16; // ecx
  _QWORD v18[2]; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v19; // [rsp+68h] [rbp-50h]
  int v20; // [rsp+6Ch] [rbp-4Ch]
  unsigned int *v21; // [rsp+70h] [rbp-48h]
  SIZE_T NumberOfBytesRead; // [rsp+C8h] [rbp+10h] BYREF
  char *v24; // [rsp+D0h] [rbp+18h]

  v5 = a4;
  v6 = a3;
  v7 = a2;
  v8 = 0;
  v20 = 0;
  v18[0] = a2;
  v18[1] = a3;
  v19 = a4;
  v9 = a5;
  v21 = a5;
  v10 = 0;
  *a5 = a4 + 1;
  ProcessEntry = FindProcessEntry(a1);
  v12 = ProcessEntry;
  if ( ProcessEntry )
  {
    v13 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD))*((_QWORD *)ProcessEntry + 9);
    if ( v13
      || (v13 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD))*((_QWORD *)v12 + 10)) != 0
      || (v13 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD))*((_QWORD *)v12 + 11)) != 0 )
    {
      v10 = v13(*((_QWORD *)v12 + 6), 6, v18, *((_QWORD *)v12 + 12));
    }
    if ( !v10 || *v9 == v5 + 1 )
    {
      if ( *((_DWORD *)v12 + 14) )
      {
        v24 = v7;
        v10 = 1;
        v14 = 0;
        NumberOfBytesRead = 0;
        for ( i = 0; ; i += NumberOfBytesRead )
        {
          v24 = v7;
          if ( !v5 )
            break;
          v16 = 4096 - ((unsigned __int16)v7 & 0xFFF);
          if ( v5 < v16 )
            v16 = v5;
          if ( !ReadProcessMemory(a1, v7, v6, v16, &NumberOfBytesRead) )
          {
            if ( !i )
              v10 = 0;
            break;
          }
          v14 = NumberOfBytesRead + i;
          v7 += NumberOfBytesRead;
          v24 = v7;
          v6 += NumberOfBytesRead;
          v5 -= NumberOfBytesRead;
        }
        *a5 = v14;
      }
      else
      {
        v10 = 0;
      }
    }
    LOBYTE(v8) = v10 != 0;
    return v8;
  }
  else
  {
    SetLastError(6u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ad30  mov     rax, rsp
0x18000ad33  mov     [rax+8], rcx
0x18000ad37  push    rbx
0x18000ad38  push    rsi
0x18000ad39  push    rdi
0x18000ad3a  push    r12
0x18000ad3c  push    r13
0x18000ad3e  push    r14
0x18000ad40  push    r15
0x18000ad42  sub     rsp, 80h
0x18000ad49  mov     r14d, r9d
0x18000ad4c  mov     r12, r8
0x18000ad4f  mov     r15, rdx
0x18000ad52  xor     ebx, ebx
0x18000ad54  mov     [rax-4Ch], ebx
0x18000ad57  mov     [rax-60h], rdx
0x18000ad5b  mov     [rax-58h], r8
0x18000ad5f  mov     [rax-50h], r9d
0x18000ad63  mov     r13, [rsp+0B8h+arg_20]
0x18000ad6b  mov     [rax-48h], r13
0x18000ad6f  mov     edi, ebx
0x18000ad71  lea     eax, [r9+1]
0x18000ad75  mov     [r13+0], eax
0x18000ad79  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000ad7e  mov     rsi, rax
0x18000ad81  test    rax, rax
0x18000ad84  jz      loc_18000AEAC
0x18000ad8a  mov     rax, [rax+48h]
0x18000ad8e  test    rax, rax
0x18000ad91  jnz     short loc_18000ADA5
0x18000ad93  mov     rax, [rsi+50h]
0x18000ad97  test    rax, rax
0x18000ad9a  jnz     short loc_18000ADA5
0x18000ad9c  mov     rax, [rsi+58h]
0x18000ada0  test    rax, rax
0x18000ada3  jz      short loc_18000ADC2
0x18000ada5  mov     r9, [rsi+60h]
0x18000ada9  lea     r8, [rsp+0B8h+var_60]
0x18000adae  mov     edx, 6
0x18000adb3  mov     rcx, [rsi+30h]
0x18000adb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adbc  mov     edi, eax
0x18000adbe  mov     [rsp+0B8h+var_88], eax
0x18000adc2  test    edi, edi
0x18000adc4  jnz     loc_18000AE9C
0x18000adca  cmp     [rsi+38h], ebx
0x18000adcd  jz      loc_18000AEBB
0x18000add3  mov     [rsp+0B8h+var_80], r14d
0x18000add8  mov     [rsp+0B8h+var_70], r12
0x18000addd  mov     [rsp+0B8h+arg_10], r15
0x18000ade5  mov     edi, 1
0x18000adea  mov     [rsp+0B8h+var_84], edi
0x18000adee  mov     rsi, rbx
0x18000adf1  mov     [rsp+0B8h+var_78], rbx
0x18000adf6  mov     [rsp+0B8h+NumberOfBytesRead], rbx
0x18000adfe  mov     r13, rbx
0x18000ae01  mov     [rsp+0B8h+arg_10], r15
0x18000ae09  test    r14d, r14d
0x18000ae0c  jz      short loc_18000AE88
0x18000ae0e  mov     eax, r15d
0x18000ae11  and     eax, 0FFFh
0x18000ae16  mov     ecx, 1000h
0x18000ae1b  sub     ecx, eax
0x18000ae1d  cmp     r14d, ecx
0x18000ae20  cmovb   ecx, r14d
0x18000ae24  mov     r9d, ecx; nSize
0x18000ae27  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x18000ae2f  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000ae34  mov     r8, r12; lpBuffer
0x18000ae37  mov     rdx, r15; lpBaseAddress
0x18000ae3a  mov     rcx, [rsp+0B8h+hProcess]; hProcess
0x18000ae42  call    cs:__imp_ReadProcessMemory
0x18000ae48  test    eax, eax
0x18000ae4a  jz      short loc_18000AE7D
0x18000ae4c  mov     rax, [rsp+0B8h+NumberOfBytesRead]
0x18000ae54  lea     rsi, [rax+r13]
0x18000ae58  mov     [rsp+0B8h+var_78], rsi
0x18000ae5d  add     r15, rax
0x18000ae60  mov     [rsp+0B8h+arg_10], r15
0x18000ae68  add     r12, rax
0x18000ae6b  mov     [rsp+0B8h+var_70], r12
0x18000ae70  sub     r14d, eax
0x18000ae73  mov     [rsp+0B8h+var_80], r14d
0x18000ae78  mov     r13, rsi
0x18000ae7b  jmp     short loc_18000AE01
0x18000ae7d  test    r13, r13
0x18000ae80  jnz     short loc_18000AE88
0x18000ae82  mov     edi, ebx
0x18000ae84  mov     [rsp+0B8h+var_84], ebx
0x18000ae88  mov     [rsp+0B8h+var_68], esi
0x18000ae8c  mov     [rsp+0B8h+var_88], edi
0x18000ae90  mov     rax, [rsp+0B8h+arg_20]
0x18000ae98  mov     [rax], esi
0x18000ae9a  jmp     short loc_18000AEC1
0x18000ae9c  lea     eax, [r14+1]
0x18000aea0  cmp     [r13+0], eax
0x18000aea4  jz      loc_18000ADCA
0x18000aeaa  jmp     short loc_18000AEC1
0x18000aeac  mov     ecx, 6; dwErrCode
0x18000aeb1  call    cs:__imp_SetLastError
0x18000aeb7  xor     eax, eax
0x18000aeb9  jmp     short loc_18000AED2
0x18000aebb  mov     edi, ebx
0x18000aebd  mov     [rsp+0B8h+var_88], ebx
0x18000aec1  jmp     short loc_18000AECB
0x18000aec3  xor     edi, edi
0x18000aec5  mov     [rsp+0B8h+var_88], edi
0x18000aec9  xor     ebx, ebx
0x18000aecb  test    edi, edi
0x18000aecd  setnz   bl
0x18000aed0  mov     eax, ebx
0x18000aed2  add     rsp, 80h
0x18000aed9  pop     r15
0x18000aedb  pop     r14
0x18000aedd  pop     r13
0x18000aedf  pop     r12
0x18000aee1  pop     rdi
0x18000aee2  pop     rsi
0x18000aee3  pop     rbx
0x18000aee4  retn
```
