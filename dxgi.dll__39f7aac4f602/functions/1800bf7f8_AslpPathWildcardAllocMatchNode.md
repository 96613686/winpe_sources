# AslpPathWildcardAllocMatchNode

- ea: `0x1800bf7f8`
- end: `0x1800bfa7e`
- name: `AslpPathWildcardAllocMatchNode`
- size: `646`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800be468`
- `0x1800be9d0`

## callees

- `0x18004281c`
- `0x1800bf7f8`
- `0x1800bfb78`
- `0x1800bff54`
- `0x1800bff78`
- `0x1800c0018`
- `0x1800c00d4`
- `0x1800c0188`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800bf8f3`
- `ntdll!RtlAllocateHeap` at `0x1800bf8f3`
- `ntdll!ZwOpenFile` at `0x1800bfa2e`
- `ntdll!ZwOpenFile` at `0x1800bfa2e`

## string_xrefs

- `0x1800bfa4b`: `AslpPathWildcardAllocMatchNode`
- `0x1800bf91d`: `RtlUnicodeStringCopy failed [%x]`
- `0x1800bfa3a`: `Failed to open dir [%x]`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        __int64 a5,
        unsigned __int16 a6)
{
  int v8; // edi
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // ecx
  PVOID Heap; // rax
  __int16 v14; // bx
  ULONG ShareAccess[2]; // [rsp+20h] [rbp-60h]
  __int64 v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 3) = 0;
  while ( 1 )
  {
    *((_QWORD *)a1 + 2) = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *((_QWORD *)a1 + 2) = a3 + 1;
  if ( !a3[1] )
  {
    v8 = a4 != 0 ? -1073741638 : -1073741197;
LABEL_27:
    AslpPathWildcardFreeMatchNode(a1);
    return (unsigned int)v8;
  }
  if ( !a4 )
  {
    v8 = -1073741565;
    goto LABEL_27;
  }
  LOWORD(v21) = *a2;
  v9 = RtlUShortAdd((unsigned __int16)v21, a6, &v21);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2886;
LABEL_26:
    ShareAccess[0] = v9;
    AslLogCallPrintf(1, "AslpPathWildcardAllocMatchNode", v11, v10, *(_QWORD *)ShareAccess);
    goto LABEL_27;
  }
  v9 = RtlUShortAdd((unsigned __int16)v21, 4, &v21);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2892;
    goto LABEL_26;
  }
  v12 = (unsigned __int16)v21;
  a1[1] = v21;
  *a1 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
  *((_QWORD *)a1 + 1) = Heap;
  if ( !Heap )
  {
    v8 = -1073741801;
    goto LABEL_27;
  }
  v9 = RtlUnicodeStringCopy(a1, a2);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUnicodeStringCopy failed [%x]";
    v11 = 2907;
    goto LABEL_26;
  }
  if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1) - 2) != 92 )
  {
    v17 = 0;
    v21 = 0;
    v22 = 0;
    v8 = RtlUnicodeStringValidateDestWorker(a1, &v17, &v21, &v22);
    if ( v8 < 0
      || (v14 = v22,
          v18 = 0,
          v8 = RtlWideCharArrayCopyStringWorker(
                 (int)v17 + 2 * (int)v22,
                 (int)v21 - (int)v22,
                 (unsigned int)&v18,
                 (unsigned int)L"\\",
                 0x7FFF),
          *a1 = 2 * (v18 + v14),
          v8 < 0) )
    {
      ShareAccess[0] = v8;
      AslLogCallPrintf(
        1,
        "AslpPathWildcardAllocMatchNode",
        2923,
        "RtlUnicodeStringCatString failed [%x]",
        *(_QWORD *)ShareAccess);
      goto LABEL_27;
    }
  }
  if ( a5 )
  {
    if ( a6 )
    {
      v9 = RtlUnicodeStringCbCatStringN(a1, a5, a6);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = "RtlUnicodeStringCbCatStringN failed [%x]";
        v11 = 2931;
        goto LABEL_26;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenFile((PHANDLE)a1 + 3, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "Failed to open dir [%x]";
    v11 = 2945;
    goto LABEL_26;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800bf7f8  mov     [rsp-18h+arg_8], rbx
0x1800bf7fd  mov     [rsp-18h+arg_18], rsi
0x1800bf802  push    rbp
0x1800bf803  push    rdi
0x1800bf804  push    r15
0x1800bf806  mov     rbp, rsp
0x1800bf809  sub     rsp, 80h
0x1800bf810  xorps   xmm0, xmm0
0x1800bf813  xor     eax, eax
0x1800bf815  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800bf819  xor     r15d, r15d
0x1800bf81c  mov     rbx, rdx
0x1800bf81f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800bf823  mov     rsi, rcx
0x1800bf826  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800bf82a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800bf82e  mov     [rcx], r15
0x1800bf831  mov     [rcx+8], r15
0x1800bf835  mov     [rcx+18h], r15
0x1800bf839  jmp     short loc_1800BF83F
0x1800bf83b  add     r8, 2
0x1800bf83f  mov     [rcx+10h], r8
0x1800bf843  cmp     [r8], r15w
0x1800bf847  jnz     short loc_1800BF83B
0x1800bf849  lea     rax, [r8+2]
0x1800bf84d  mov     [rcx+10h], rax
0x1800bf851  cmp     [rax], r15w
0x1800bf855  jnz     short loc_1800BF86D
0x1800bf857  neg     r9d
0x1800bf85a  sbb     edi, edi
0x1800bf85c  and     edi, 0FFFFFE47h
0x1800bf862  add     edi, 0C0000273h
0x1800bf868  jmp     loc_1800BFA5C
0x1800bf86d  test    r9d, r9d
0x1800bf870  jnz     short loc_1800BF87C
0x1800bf872  mov     edi, 0C0000103h
0x1800bf877  jmp     loc_1800BFA5C
0x1800bf87c  movzx   ecx, word ptr [rdx]
0x1800bf87f  lea     r8, [rbp+arg_0]
0x1800bf883  movzx   edx, [rbp+arg_28]
0x1800bf887  mov     word ptr [rbp+arg_0], cx
0x1800bf88b  call    RtlUShortAdd
0x1800bf890  mov     edi, eax
0x1800bf892  test    eax, eax
0x1800bf894  jns     short loc_1800BF8A8
0x1800bf896  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1800bf89d  mov     r8d, 0B46h
0x1800bf8a3  jmp     loc_1800BFA47
0x1800bf8a8  movzx   ecx, word ptr [rbp+arg_0]
0x1800bf8ac  lea     r8, [rbp+arg_0]
0x1800bf8b0  mov     edx, 4
0x1800bf8b5  call    RtlUShortAdd
0x1800bf8ba  mov     edi, eax
0x1800bf8bc  test    eax, eax
0x1800bf8be  jns     short loc_1800BF8D2
0x1800bf8c0  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1800bf8c7  mov     r8d, 0B4Ch
0x1800bf8cd  jmp     loc_1800BFA47
0x1800bf8d2  movzx   ecx, word ptr [rbp+arg_0]
0x1800bf8d6  mov     edx, 8; Flags
0x1800bf8db  mov     [rsi+2], cx
0x1800bf8df  mov     r8d, ecx; Size
0x1800bf8e2  mov     [rsi], r15w
0x1800bf8e6  mov     rcx, gs:60h
0x1800bf8ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800bf8f3  call    cs:__imp_RtlAllocateHeap
0x1800bf8f9  mov     [rsi+8], rax
0x1800bf8fd  test    rax, rax
0x1800bf900  jnz     short loc_1800BF90C
0x1800bf902  mov     edi, 0C0000017h
0x1800bf907  jmp     loc_1800BFA5C
0x1800bf90c  mov     rdx, rbx
0x1800bf90f  mov     rcx, rsi
0x1800bf912  call    RtlUnicodeStringCopy
0x1800bf917  mov     edi, eax
0x1800bf919  test    eax, eax
0x1800bf91b  jns     short loc_1800BF92F
0x1800bf91d  lea     r9, aRtlunicodestri_1; "RtlUnicodeStringCopy failed [%x]"
0x1800bf924  mov     r8d, 0B5Bh
0x1800bf92a  jmp     loc_1800BFA47
0x1800bf92f  movzx   ecx, word ptr [rsi]
0x1800bf932  mov     rax, [rsi+8]
0x1800bf936  shr     rcx, 1
0x1800bf939  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800bf93f  jz      short loc_1800BF9BD
0x1800bf941  lea     r9, [rbp+arg_10]
0x1800bf945  mov     [rbp+var_50], r15
0x1800bf949  lea     r8, [rbp+arg_0]
0x1800bf94d  mov     [rbp+arg_0], r15
0x1800bf951  lea     rdx, [rbp+var_50]
0x1800bf955  mov     [rbp+arg_10], r15
0x1800bf959  mov     rcx, rsi
0x1800bf95c  call    RtlUnicodeStringValidateDestWorker
0x1800bf961  mov     edi, eax
0x1800bf963  test    eax, eax
0x1800bf965  js      short loc_1800BF9A7
0x1800bf967  mov     rbx, [rbp+arg_10]
0x1800bf96b  lea     r9, pszSrch; "\\"
0x1800bf972  mov     rax, [rbp+var_50]
0x1800bf976  lea     r8, [rbp+var_48]
0x1800bf97a  mov     rdx, [rbp+arg_0]
0x1800bf97e  sub     rdx, rbx
0x1800bf981  mov     [rbp+var_48], r15
0x1800bf985  mov     qword ptr [rsp+80h+ShareAccess], 7FFFh
0x1800bf98e  lea     rcx, [rax+rbx*2]
0x1800bf992  call    RtlWideCharArrayCopyStringWorker
0x1800bf997  add     bx, word ptr [rbp+var_48]
0x1800bf99b  mov     edi, eax
0x1800bf99d  add     bx, bx
0x1800bf9a0  mov     [rsi], bx
0x1800bf9a3  test    eax, eax
0x1800bf9a5  jns     short loc_1800BF9BD
0x1800bf9a7  mov     [rsp+80h+ShareAccess], edi
0x1800bf9ab  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x1800bf9b2  mov     r8d, 0B6Bh
0x1800bf9b8  jmp     loc_1800BFA4B
0x1800bf9bd  mov     rdx, [rbp+arg_20]
0x1800bf9c1  test    rdx, rdx
0x1800bf9c4  jz      short loc_1800BF9EF
0x1800bf9c6  cmp     [rbp+arg_28], r15w
0x1800bf9cb  jbe     short loc_1800BF9EF
0x1800bf9cd  movzx   r8d, [rbp+arg_28]
0x1800bf9d2  mov     rcx, rsi
0x1800bf9d5  call    RtlUnicodeStringCbCatStringN
0x1800bf9da  mov     edi, eax
0x1800bf9dc  test    eax, eax
0x1800bf9de  jns     short loc_1800BF9EF
0x1800bf9e0  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x1800bf9e7  mov     r8d, 0B73h
0x1800bf9ed  jmp     short loc_1800BFA47
0x1800bf9ef  xorps   xmm0, xmm0
0x1800bf9f2  mov     [rsp+80h+OpenOptions], 21h ; '!'; OpenOptions
0x1800bf9fa  lea     rcx, [rsi+18h]; FileHandle
0x1800bf9fe  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800bfa05  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800bfa09  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1800bfa0d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800bfa11  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800bfa18  mov     edx, 100001h; DesiredAccess
0x1800bfa1d  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x1800bfa21  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800bfa26  mov     [rsp+80h+ShareAccess], 1; ShareAccess
0x1800bfa2e  call    cs:__imp_ZwOpenFile
0x1800bfa34  mov     edi, eax
0x1800bfa36  test    eax, eax
0x1800bfa38  jns     short loc_1800BFA64
0x1800bfa3a  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x1800bfa41  mov     r8d, 0B81h
0x1800bfa47  mov     [rsp+80h+ShareAccess], eax
0x1800bfa4b  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x1800bfa52  mov     ecx, 1
0x1800bfa57  call    AslLogCallPrintf
0x1800bfa5c  mov     rcx, rsi
0x1800bfa5f  call    AslpPathWildcardFreeMatchNode
0x1800bfa64  lea     r11, [rsp+80h+var_s0]
0x1800bfa6c  mov     eax, edi
0x1800bfa6e  mov     rbx, [r11+28h]
0x1800bfa72  mov     rsi, [r11+38h]
0x1800bfa76  mov     rsp, r11
0x1800bfa79  pop     r15
0x1800bfa7b  pop     rdi
0x1800bfa7c  pop     rbp
0x1800bfa7d  retn
```
