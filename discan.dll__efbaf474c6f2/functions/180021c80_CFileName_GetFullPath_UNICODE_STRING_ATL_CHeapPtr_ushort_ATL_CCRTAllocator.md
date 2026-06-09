# CFileName::GetFullPath(_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)

- ea: `0x180021c80`
- end: `0x180021dac`
- name: `?GetFullPath@CFileName@@QEAAJPEAU_UNICODE_STRING@@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180027858`

## callees

- `0x18000f478`
- `0x180021c80`
- `0x180027160`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180021d62`
- `ntdll!RtlCopyUnicodeString` at `0x180021d8d`
- `ntdll!RtlCopyUnicodeString` at `0x180021d62`
- `ntdll!RtlCopyUnicodeString` at `0x180021d8d`

## pseudocode

```c
__int64 __fastcall CFileName::GetFullPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned __int16 v3; // bx
  __int64 v6; // rsi
  __int64 v7; // r9
  __int64 result; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  WCHAR *Buffer; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int16 v13; // [rsp+70h] [rbp+38h] BYREF

  v3 = 0;
  v13 = 0;
  *(_WORD *)a2 = 0;
  v6 = a1;
  v7 = a1;
  while ( v7 )
  {
    result = UShortAdd(v3, *(_WORD *)(v7 + 24), &v13);
    if ( (int)result < 0 )
      return result;
    v7 = *(_QWORD *)(v9 + 16);
    if ( v7 )
    {
      result = UShortAdd(v13, 2u, &v13);
      if ( (int)result < 0 )
        return result;
    }
    v3 = v13;
  }
  if ( *(_WORD *)(a2 + 2) < v3 )
  {
    if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CCRTAllocator>::ReallocateBytes(a3, v3, a3) )
      return 2147942414LL;
    *(_QWORD *)(a2 + 8) = *a3;
    *(_WORD *)(a2 + 2) = v3;
  }
  v10 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)&DestinationString.Length = 0;
  Buffer = (WCHAR *)(v10 + 2 * ((unsigned __int64)v3 >> 1));
  DestinationString.Buffer = Buffer;
  if ( v6 )
  {
    while ( 1 )
    {
      DestinationString.Buffer = &Buffer[-((unsigned __int64)*(unsigned __int16 *)(v6 + 24) >> 1)];
      DestinationString.Length = 0;
      DestinationString.MaximumLength = *(_WORD *)(v6 + 24);
      RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v6 + 24));
      *(_WORD *)a2 += *(_WORD *)(v6 + 24);
      v6 = *(_QWORD *)(v6 + 16);
      if ( !v6 )
        break;
      --DestinationString.Buffer;
      *(_DWORD *)&DestinationString.Length = 0x20000;
      RtlCopyUnicodeString(&DestinationString, &BackslashString);
      *(_WORD *)a2 += 2;
      Buffer = DestinationString.Buffer;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021c80  push    rbp
0x180021c82  push    rbx
0x180021c83  push    rsi
0x180021c84  push    rdi
0x180021c85  push    r14
0x180021c87  push    r15
0x180021c89  mov     rbp, rsp
0x180021c8c  sub     rsp, 38h
0x180021c90  xor     ebx, ebx
0x180021c92  mov     r14, r8
0x180021c95  xor     eax, eax
0x180021c97  mov     [rbp+arg_0], bx
0x180021c9b  mov     rdi, rdx
0x180021c9e  mov     [rdx], ax
0x180021ca1  mov     rsi, rcx
0x180021ca4  mov     r9, rcx
0x180021ca7  lea     r15d, [rbx+2]
0x180021cab  test    r9, r9
0x180021cae  jz      short loc_180021CF0
0x180021cb0  movzx   edx, word ptr [r9+18h]; unsigned __int16
0x180021cb5  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180021cb9  movzx   ecx, bx; unsigned __int16
0x180021cbc  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x180021cc1  test    eax, eax
0x180021cc3  js      loc_180021D9F
0x180021cc9  mov     r9, [r9+10h]
0x180021ccd  test    r9, r9
0x180021cd0  jz      short loc_180021CEA
0x180021cd2  movzx   ecx, [rbp+arg_0]; unsigned __int16
0x180021cd6  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180021cda  mov     edx, r15d; unsigned __int16
0x180021cdd  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x180021ce2  test    eax, eax
0x180021ce4  js      loc_180021D9F
0x180021cea  movzx   ebx, [rbp+arg_0]
0x180021cee  jmp     short loc_180021CAB
0x180021cf0  cmp     [rdi+2], bx
0x180021cf4  jnb     short loc_180021D1A
0x180021cf6  movzx   edx, bx
0x180021cf9  mov     rcx, r14
0x180021cfc  call    ?ReallocateBytes@?$CHeapPtrBase@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CCRTAllocator>::ReallocateBytes(unsigned __int64)
0x180021d01  test    al, al
0x180021d03  jnz     short loc_180021D0F
0x180021d05  mov     eax, 8007000Eh
0x180021d0a  jmp     loc_180021D9F
0x180021d0f  mov     rax, [r14]
0x180021d12  mov     [rdi+8], rax
0x180021d16  mov     [rdi+2], bx
0x180021d1a  mov     rax, [rdi+8]
0x180021d1e  movzx   ecx, bx
0x180021d21  shr     rcx, 1
0x180021d24  mov     qword ptr [rbp+DestinationString.Length], 0
0x180021d2c  lea     rdx, [rax+rcx*2]
0x180021d30  mov     [rbp+DestinationString.Buffer], rdx
0x180021d34  test    rsi, rsi
0x180021d37  jz      short loc_180021D9D
0x180021d39  lea     rbx, [rsi+18h]
0x180021d3d  movzx   eax, word ptr [rbx]
0x180021d40  lea     rcx, [rbp+DestinationString]; DestinationString
0x180021d44  shr     rax, 1
0x180021d47  neg     rax
0x180021d4a  lea     rax, [rdx+rax*2]
0x180021d4e  mov     rdx, rbx; SourceString
0x180021d51  mov     [rbp+DestinationString.Buffer], rax
0x180021d55  xor     eax, eax
0x180021d57  mov     [rbp+DestinationString.Length], ax
0x180021d5b  movzx   eax, word ptr [rbx]
0x180021d5e  mov     [rbp+DestinationString.MaximumLength], ax
0x180021d62  call    cs:__imp_RtlCopyUnicodeString
0x180021d68  movzx   eax, word ptr [rbx]
0x180021d6b  add     [rdi], ax
0x180021d6e  mov     rsi, [rsi+10h]
0x180021d72  test    rsi, rsi
0x180021d75  jz      short loc_180021D9D
0x180021d77  sub     [rbp+DestinationString.Buffer], r15
0x180021d7b  lea     rdx, ?BackslashString@@3U_UNICODE_STRING@@B; SourceString
0x180021d82  lea     rcx, [rbp+DestinationString]; DestinationString
0x180021d86  mov     dword ptr [rbp+DestinationString.Length], 20000h
0x180021d8d  call    cs:__imp_RtlCopyUnicodeString
0x180021d93  add     [rdi], r15w
0x180021d97  mov     rdx, [rbp+DestinationString.Buffer]
0x180021d9b  jmp     short loc_180021D39
0x180021d9d  xor     eax, eax
0x180021d9f  add     rsp, 38h
0x180021da3  pop     r15
0x180021da5  pop     r14
0x180021da7  pop     rdi
0x180021da8  pop     rsi
0x180021da9  pop     rbx
0x180021daa  pop     rbp
0x180021dab  retn
```
