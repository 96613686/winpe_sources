# sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success

- ea: `0x18007e01c`
- end: `0x18007e167`
- name: `sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success`
- size: `331`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bcb0`

## callees

- `0x180035fd0`
- `0x18007e01c`
- `0x18007e170`
- `0x18016f030`

## string_xrefs

- `0x18007e099`: `minkernel\ntdll\sxsisol.cpp`
- `0x18007e0e8`: `minkernel\ntdll\sxsisol.cpp`

## pseudocode

```c
__int64 __fastcall sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success(_BYTE *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  unsigned int v5; // edi
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rax
  wchar_t **v10; // rdi
  wchar_t *v11; // rax
  _WORD *v12; // rcx
  UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
  {
    RtlAssert("Internal error check failed", "minkernel\\ntdll\\sxsisol.cpp", 523, "This != NULL");
    return (unsigned int)-1073741595;
  }
  if ( !a1[80] )
    goto LABEL_8;
  v2 = *((_QWORD *)a1 + 8);
  if ( v2 && *(_QWORD *)(v2 + 8) )
  {
    v7 = "(This->PrivateDynamicallyAllocatedString == NULL) || (This->PrivateDynamicallyAllocatedString->Buffer == NULL)";
    v8 = 531;
    goto LABEL_12;
  }
  v3 = *((_QWORD *)a1 + 7);
  if ( v3 && *(_QWORD *)(v3 + 8) == *((_QWORD *)a1 + 1) )
  {
    if ( *(_WORD *)a1 <= *(_WORD *)(v3 + 2) )
    {
      *(_WORD *)v3 = *(_WORD *)a1;
      v4 = (_QWORD *)*((_QWORD *)a1 + 9);
      if ( v4 )
      {
        v9 = *((_QWORD *)a1 + 7);
LABEL_17:
        *v4 = v9;
        goto LABEL_8;
      }
      goto LABEL_8;
    }
    v7 = "rUS.Length <= This->PrivatePreallocatedString->MaximumLength";
    v8 = 536;
LABEL_12:
    RtlAssert("Internal error check failed", "minkernel\\ntdll\\sxsisol.cpp", v8, v7);
    v5 = -1073741595;
    goto LABEL_9;
  }
  if ( !v2 )
  {
    v10 = (wchar_t **)(a1 + 16);
    if ( a1 != (_BYTE *)-16LL )
    {
      v11 = *v10;
      if ( *v10 )
      {
        if ( v11 != *((wchar_t **)a1 + 3) )
        {
          *(_QWORD *)&UnicodeString.Length = 0;
          UnicodeString.Buffer = v11;
          RtlFreeAnsiString(&UnicodeString);
        }
        *v10 = (wchar_t *)*((_QWORD *)a1 + 3);
      }
    }
    v12 = (_WORD *)*((_QWORD *)a1 + 3);
    if ( v12 )
      *v12 = 0;
    goto LABEL_8;
  }
  *(_OWORD *)v2 = *(_OWORD *)a1;
  v4 = (_QWORD *)*((_QWORD *)a1 + 9);
  if ( v4 )
  {
    v9 = *((_QWORD *)a1 + 8);
    goto LABEL_17;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  memset_thunk_772440563353939046(a1, 0, 0x58u);
  return v5;
}

```

## disassembly

```asm
0x18007e01c  mov     [rsp+arg_0], rbx
0x18007e021  push    rdi
0x18007e022  sub     rsp, 30h
0x18007e026  mov     rbx, rcx
0x18007e029  test    rcx, rcx
0x18007e02c  jz      loc_18007E0DB
0x18007e032  cmp     byte ptr [rcx+50h], 0
0x18007e036  jz      short loc_18007E06E
0x18007e038  mov     rcx, [rcx+40h]
0x18007e03c  test    rcx, rcx
0x18007e03f  jz      short loc_18007E048
0x18007e041  cmp     qword ptr [rcx+8], 0
0x18007e046  jnz     short loc_18007E08C
0x18007e048  mov     rdx, [rbx+38h]
0x18007e04c  test    rdx, rdx
0x18007e04f  jnz     short loc_18007E0B3
0x18007e051  test    rcx, rcx
0x18007e054  jz      loc_18007E11A
0x18007e05a  movaps  xmm0, xmmword ptr [rbx]
0x18007e05d  movdqu  xmmword ptr [rcx], xmm0
0x18007e061  mov     rcx, [rbx+48h]
0x18007e065  test    rcx, rcx
0x18007e068  jnz     loc_18007E114
0x18007e06e  xor     edi, edi
0x18007e070  xor     edx, edx; Val
0x18007e072  mov     rcx, rbx; void *
0x18007e075  lea     r8d, [rdx+58h]; Size
0x18007e079  call    memset$thunk$772440563353939046
0x18007e07e  mov     rbx, [rsp+38h+arg_0]
0x18007e083  mov     eax, edi
0x18007e085  add     rsp, 30h
0x18007e089  pop     rdi
0x18007e08a  retn
0x18007e08c  lea     r9, aThisPrivatedyn; "(This->PrivateDynamicallyAllocatedStrin"...
0x18007e093  mov     r8d, 213h
0x18007e099  lea     rdx, aMinkernelNtdll; "minkernel\\ntdll\\sxsisol.cpp"
0x18007e0a0  lea     rcx, aInternalErrorC; "Internal error check failed"
0x18007e0a7  call    RtlAssert
0x18007e0ac  mov     edi, 0C00000E5h
0x18007e0b1  jmp     short loc_18007E070
0x18007e0b3  mov     rax, [rbx+8]
0x18007e0b7  cmp     [rdx+8], rax
0x18007e0bb  jnz     short loc_18007E051
0x18007e0bd  movzx   eax, word ptr [rbx]
0x18007e0c0  cmp     ax, [rdx+2]
0x18007e0c4  ja      short loc_18007E105
0x18007e0c6  mov     [rdx], ax
0x18007e0c9  mov     rcx, [rbx+48h]
0x18007e0cd  test    rcx, rcx
0x18007e0d0  jz      short loc_18007E06E
0x18007e0d2  mov     rax, [rbx+38h]
0x18007e0d6  mov     [rcx], rax
0x18007e0d9  jmp     short loc_18007E06E
0x18007e0db  lea     r9, aThisNull; "This != NULL"
0x18007e0e2  mov     r8d, 20Bh
0x18007e0e8  lea     rdx, aMinkernelNtdll; "minkernel\\ntdll\\sxsisol.cpp"
0x18007e0ef  lea     rcx, aInternalErrorC; "Internal error check failed"
0x18007e0f6  call    RtlAssert
0x18007e0fb  mov     edi, 0C00000E5h
0x18007e100  jmp     loc_18007E07E
0x18007e105  lea     r9, aRusLengthThisP; "rUS.Length <= This->PrivatePreallocated"...
0x18007e10c  mov     r8d, 218h
0x18007e112  jmp     short loc_18007E099
0x18007e114  mov     rax, [rbx+40h]
0x18007e118  jmp     short loc_18007E0D6
0x18007e11a  lea     rdi, [rbx+10h]
0x18007e11e  test    rdi, rdi
0x18007e121  jz      short loc_18007E150
0x18007e123  mov     rax, [rdi]
0x18007e126  test    rax, rax
0x18007e129  jz      short loc_18007E150
0x18007e12b  cmp     rax, [rbx+18h]
0x18007e12f  jz      short loc_18007E149
0x18007e131  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18007e136  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x18007e13f  mov     [rsp+38h+UnicodeString.Buffer], rax
0x18007e144  call    RtlFreeAnsiString
0x18007e149  mov     rax, [rbx+18h]
0x18007e14d  mov     [rdi], rax
0x18007e150  mov     rcx, [rbx+18h]
0x18007e154  test    rcx, rcx
0x18007e157  jz      loc_18007E06E
0x18007e15d  xor     eax, eax
0x18007e15f  mov     [rcx], ax
0x18007e162  jmp     loc_18007E06E
```
