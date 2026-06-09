# sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success

- ea: `0x18006163c`
- end: `0x180061787`
- name: `sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success`
- size: `331`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bcb0`

## callees

- `0x180036e70`
- `0x18006163c`
- `0x180061790`
- `0x18016f030`

## string_xrefs

- `0x1800616b9`: `minkernel\ntdll\sxsisol.cpp`
- `0x180061708`: `minkernel\ntdll\sxsisol.cpp`

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
0x18006163c  mov     [rsp+arg_0], rbx
0x180061641  push    rdi
0x180061642  sub     rsp, 30h
0x180061646  mov     rbx, rcx
0x180061649  test    rcx, rcx
0x18006164c  jz      loc_1800616FB
0x180061652  cmp     byte ptr [rcx+50h], 0
0x180061656  jz      short loc_18006168E
0x180061658  mov     rcx, [rcx+40h]
0x18006165c  test    rcx, rcx
0x18006165f  jz      short loc_180061668
0x180061661  cmp     qword ptr [rcx+8], 0
0x180061666  jnz     short loc_1800616AC
0x180061668  mov     rdx, [rbx+38h]
0x18006166c  test    rdx, rdx
0x18006166f  jnz     short loc_1800616D3
0x180061671  test    rcx, rcx
0x180061674  jz      loc_18006173A
0x18006167a  movaps  xmm0, xmmword ptr [rbx]
0x18006167d  movdqu  xmmword ptr [rcx], xmm0
0x180061681  mov     rcx, [rbx+48h]
0x180061685  test    rcx, rcx
0x180061688  jnz     loc_180061734
0x18006168e  xor     edi, edi
0x180061690  xor     edx, edx; Val
0x180061692  mov     rcx, rbx; void *
0x180061695  lea     r8d, [rdx+58h]; Size
0x180061699  call    memset$thunk$772440563353939046
0x18006169e  mov     rbx, [rsp+38h+arg_0]
0x1800616a3  mov     eax, edi
0x1800616a5  add     rsp, 30h
0x1800616a9  pop     rdi
0x1800616aa  retn
0x1800616ac  lea     r9, aThisPrivatedyn; "(This->PrivateDynamicallyAllocatedStrin"...
0x1800616b3  mov     r8d, 213h
0x1800616b9  lea     rdx, aMinkernelNtdll; "minkernel\\ntdll\\sxsisol.cpp"
0x1800616c0  lea     rcx, aInternalErrorC; "Internal error check failed"
0x1800616c7  call    RtlAssert
0x1800616cc  mov     edi, 0C00000E5h
0x1800616d1  jmp     short loc_180061690
0x1800616d3  mov     rax, [rbx+8]
0x1800616d7  cmp     [rdx+8], rax
0x1800616db  jnz     short loc_180061671
0x1800616dd  movzx   eax, word ptr [rbx]
0x1800616e0  cmp     ax, [rdx+2]
0x1800616e4  ja      short loc_180061725
0x1800616e6  mov     [rdx], ax
0x1800616e9  mov     rcx, [rbx+48h]
0x1800616ed  test    rcx, rcx
0x1800616f0  jz      short loc_18006168E
0x1800616f2  mov     rax, [rbx+38h]
0x1800616f6  mov     [rcx], rax
0x1800616f9  jmp     short loc_18006168E
0x1800616fb  lea     r9, aThisNull; "This != NULL"
0x180061702  mov     r8d, 20Bh
0x180061708  lea     rdx, aMinkernelNtdll; "minkernel\\ntdll\\sxsisol.cpp"
0x18006170f  lea     rcx, aInternalErrorC; "Internal error check failed"
0x180061716  call    RtlAssert
0x18006171b  mov     edi, 0C00000E5h
0x180061720  jmp     loc_18006169E
0x180061725  lea     r9, aRusLengthThisP; "rUS.Length <= This->PrivatePreallocated"...
0x18006172c  mov     r8d, 218h
0x180061732  jmp     short loc_1800616B9
0x180061734  mov     rax, [rbx+40h]
0x180061738  jmp     short loc_1800616F6
0x18006173a  lea     rdi, [rbx+10h]
0x18006173e  test    rdi, rdi
0x180061741  jz      short loc_180061770
0x180061743  mov     rax, [rdi]
0x180061746  test    rax, rax
0x180061749  jz      short loc_180061770
0x18006174b  cmp     rax, [rbx+18h]
0x18006174f  jz      short loc_180061769
0x180061751  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180061756  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x18006175f  mov     [rsp+38h+UnicodeString.Buffer], rax
0x180061764  call    RtlFreeAnsiString
0x180061769  mov     rax, [rbx+18h]
0x18006176d  mov     [rdi], rax
0x180061770  mov     rcx, [rbx+18h]
0x180061774  test    rcx, rcx
0x180061777  jz      loc_18006168E
0x18006177d  xor     eax, eax
0x18006177f  mov     [rcx], ax
0x180061782  jmp     loc_18006168E
```
