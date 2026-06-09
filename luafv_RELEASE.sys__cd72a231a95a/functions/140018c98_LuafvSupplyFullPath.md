# LuafvSupplyFullPath

- ea: `0x140018c98`
- end: `0x140018f17`
- name: `LuafvSupplyFullPath`
- size: `639`
- prototype: `char __fastcall(__int64, UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001892c`
- `0x140023cc4`

## callees

- `0x140005d00`
- `0x140018c98`
- `0x140019730`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018e20`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018e20`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018da2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018eb7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018da2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018eb7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018d8f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018d8f`
- `FLTMGR!FltReleaseContext` at `0x140018e6b`
- `FLTMGR!FltReleaseContext` at `0x140018ef1`
- `FLTMGR!FltReleaseContext` at `0x140018e6b`
- `FLTMGR!FltReleaseContext` at `0x140018ef1`
- `FLTMGR!FltGetInstanceContext` at `0x140018e40`
- `FLTMGR!FltGetInstanceContext` at `0x140018e40`

## pseudocode

```c
char __fastcall LuafvSupplyFullPath(__int64 a1, UNICODE_STRING *a2)
{
  char v2; // di
  bool v3; // cf
  __int64 v6; // rcx
  struct _FILE_OBJECT *v7; // rdx
  __int64 v8; // r8
  void *v9; // r14
  WCHAR *Pool; // rax
  __int64 v11; // r8
  __int64 v12; // rsi
  USHORT v13; // dx
  WCHAR *v14; // rax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+30h] [rbp-18h]
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+40h] BYREF

  v2 = 0;
  Context = 0;
  v3 = a2->Length < 2u;
  *(_OWORD *)Src = 0;
  Destination = 0;
  if ( !v3 && *a2->Buffer == 92 )
    goto LABEL_21;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(struct _FILE_OBJECT **)(v6 + 8);
  if ( v7->RelatedFileObject && !*(_BYTE *)(v6 + 4) )
  {
    if ( (int)LuafvGetNameFileObject(*(PFLT_INSTANCE *)(v6 + 16), v7->RelatedFileObject) < 0 )
      return 0;
    v9 = Src[1];
    if ( LOWORD(Src[0]) >= 2u && *(_WORD *)Src[1] == 92 && LOWORD(Src[0]) <= 0x1000u )
    {
      LOBYTE(v8) = 2;
      Destination.MaximumLength = a2->Length + LOWORD(Src[0]) + 2;
      Pool = (WCHAR *)LuafvAllocatePool(1, Destination.MaximumLength, v8);
      Destination.Buffer = Pool;
      if ( Pool )
      {
        Destination.Length = (USHORT)Src[0];
        memmove(Pool, Src[1], LOWORD(Src[0]));
        if ( Destination.Buffer[((unsigned __int64)LOWORD(Src[0]) >> 1) - 1] != 92 )
          RtlAppendUnicodeToString(&Destination, L"\\");
        if ( RtlAppendUnicodeStringToString(&Destination, a2) < 0 )
        {
          LuafvFreePool(Destination.Buffer);
        }
        else
        {
          v2 = 1;
          *a2 = Destination;
        }
      }
    }
    LuafvFreePool(v9);
    if ( !v2 )
      return 0;
    goto LABEL_21;
  }
  if ( (int)LuafvGetNameFileObject(*(PFLT_INSTANCE *)(v6 + 16), v7) >= 0 )
  {
    if ( Destination.Length < 2u || *Destination.Buffer != 92 )
    {
      LuafvFreePool(Destination.Buffer);
      return 0;
    }
    v2 = 1;
    *a2 = Destination;
LABEL_21:
    if ( !RtlPrefixUnicodeString(&LuafvDeviceNamePrefix, a2, 1u)
      && FltGetInstanceContext(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL), &Context) >= 0 )
    {
      v12 = *((_QWORD *)Context + 3);
      v13 = *(_WORD *)(v12 + 56) + a2->Length;
      if ( v13 < a2->Length )
      {
        FltReleaseContext(Context);
        return 0;
      }
      Destination.MaximumLength = *(_WORD *)(v12 + 56) + a2->Length;
      LOBYTE(v11) = 2;
      v14 = (WCHAR *)LuafvAllocatePool(1, v13, v11);
      Destination.Buffer = v14;
      if ( v14 )
      {
        Destination.Length = *(_WORD *)(v12 + 56);
        memmove(v14, *(const void **)(v12 + 64), Destination.Length);
        if ( RtlAppendUnicodeStringToString(&Destination, a2) < 0 )
        {
          LuafvFreePool(Destination.Buffer);
        }
        else
        {
          if ( v2 )
            LuafvFreePool(a2->Buffer);
          else
            v2 = 1;
          *a2 = Destination;
        }
      }
      FltReleaseContext(Context);
    }
    return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x140018c98  push    rbp
0x140018c9a  push    rbx
0x140018c9b  push    rsi
0x140018c9c  push    rdi
0x140018c9d  push    r14
0x140018c9f  push    r15
0x140018ca1  mov     rbp, rsp
0x140018ca4  sub     rsp, 48h
0x140018ca8  xor     dil, dil
0x140018cab  mov     [rbp+Context], 0
0x140018cb3  cmp     word ptr [rdx], 2
0x140018cb7  xorps   xmm0, xmm0
0x140018cba  xorps   xmm1, xmm1
0x140018cbd  mov     rbx, rdx
0x140018cc0  mov     r15, rcx
0x140018cc3  movups  xmmword ptr [rbp+Src], xmm0
0x140018cc7  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x140018ccb  jb      short loc_140018CDB
0x140018ccd  mov     rax, [rdx+8]
0x140018cd1  cmp     word ptr [rax], 5Ch ; '\'
0x140018cd5  jz      loc_140018E13
0x140018cdb  mov     rcx, [rcx+10h]
0x140018cdf  mov     rdx, [rcx+8]; FileObject
0x140018ce3  mov     rax, [rdx+40h]
0x140018ce7  test    rax, rax
0x140018cea  jz      loc_140018DDA
0x140018cf0  cmp     [rcx+4], dil
0x140018cf4  jnz     loc_140018DDA
0x140018cfa  mov     rcx, [rcx+10h]; Instance
0x140018cfe  lea     r8, [rbp+Src]
0x140018d02  mov     rdx, rax; FileObject
0x140018d05  call    LuafvGetNameFileObject
0x140018d0a  test    eax, eax
0x140018d0c  js      loc_140018F07
0x140018d12  movzx   esi, word ptr [rbp+Src]
0x140018d16  mov     r14, [rbp+Src+8]
0x140018d1a  cmp     esi, 2
0x140018d1d  jb      loc_140018DC8
0x140018d23  cmp     word ptr [r14], 5Ch ; '\'
0x140018d28  jnz     loc_140018DC8
0x140018d2e  mov     eax, 1000h
0x140018d33  cmp     si, ax
0x140018d36  ja      loc_140018DC8
0x140018d3c  lea     eax, [rsi+2]
0x140018d3f  mov     r8b, 2
0x140018d42  add     ax, [rbx]
0x140018d45  mov     ecx, 1
0x140018d4a  movzx   edx, ax
0x140018d4d  mov     [rbp+Destination.MaximumLength], dx
0x140018d51  call    LuafvAllocatePool
0x140018d56  mov     [rbp+Destination.Buffer], rax
0x140018d5a  test    rax, rax
0x140018d5d  jz      short loc_140018DC8
0x140018d5f  mov     r8d, esi; Size
0x140018d62  mov     [rbp+Destination.Length], si
0x140018d66  mov     rdx, r14; Src
0x140018d69  mov     rcx, rax; void *
0x140018d6c  call    memmove
0x140018d71  movzx   ecx, [rbp+Destination.Length]
0x140018d75  mov     rax, [rbp+Destination.Buffer]
0x140018d79  shr     rcx, 1
0x140018d7c  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140018d82  jz      short loc_140018D9B
0x140018d84  lea     rdx, Source; "\\"
0x140018d8b  lea     rcx, [rbp+Destination]; Destination
0x140018d8f  call    cs:__imp_RtlAppendUnicodeToString
0x140018d96  nop     dword ptr [rax+rax+00h]
0x140018d9b  mov     rdx, rbx; Source
0x140018d9e  lea     rcx, [rbp+Destination]; Destination
0x140018da2  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018da9  nop     dword ptr [rax+rax+00h]
0x140018dae  test    eax, eax
0x140018db0  js      short loc_140018DBF
0x140018db2  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018db6  mov     dil, 1
0x140018db9  movdqu  xmmword ptr [rbx], xmm0
0x140018dbd  jmp     short loc_140018DC8
0x140018dbf  mov     rcx, [rbp+Destination.Buffer]
0x140018dc3  call    LuafvFreePool
0x140018dc8  mov     rcx, r14
0x140018dcb  call    LuafvFreePool
0x140018dd0  test    dil, dil
0x140018dd3  jnz     short loc_140018E13
0x140018dd5  jmp     loc_140018F07
0x140018dda  mov     rcx, [rcx+10h]; Instance
0x140018dde  lea     r8, [rbp+Destination]
0x140018de2  call    LuafvGetNameFileObject
0x140018de7  test    eax, eax
0x140018de9  js      loc_140018F07
0x140018def  cmp     [rbp+Destination.Length], 2
0x140018df4  mov     rcx, [rbp+Destination.Buffer]
0x140018df8  jb      loc_140018F02
0x140018dfe  cmp     word ptr [rcx], 5Ch ; '\'
0x140018e02  jnz     loc_140018F02
0x140018e08  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018e0c  mov     dil, 1
0x140018e0f  movdqu  xmmword ptr [rbx], xmm0
0x140018e13  mov     r8b, 1; CaseInSensitive
0x140018e16  lea     rcx, LuafvDeviceNamePrefix; String1
0x140018e1d  mov     rdx, rbx; String2
0x140018e20  call    cs:__imp_RtlPrefixUnicodeString
0x140018e27  nop     dword ptr [rax+rax+00h]
0x140018e2c  test    al, al
0x140018e2e  jnz     loc_140018EFD
0x140018e34  mov     rcx, [r15+10h]
0x140018e38  lea     rdx, [rbp+Context]; Context
0x140018e3c  mov     rcx, [rcx+10h]; Instance
0x140018e40  call    cs:__imp_FltGetInstanceContext
0x140018e47  nop     dword ptr [rax+rax+00h]
0x140018e4c  test    eax, eax
0x140018e4e  js      loc_140018EFD
0x140018e54  movzx   eax, word ptr [rbx]
0x140018e57  mov     rcx, [rbp+Context]; Context
0x140018e5b  movzx   edx, ax
0x140018e5e  mov     rsi, [rcx+18h]
0x140018e62  add     dx, [rsi+38h]
0x140018e66  cmp     dx, ax
0x140018e69  jnb     short loc_140018E7C
0x140018e6b  call    cs:__imp_FltReleaseContext
0x140018e72  nop     dword ptr [rax+rax+00h]
0x140018e77  jmp     loc_140018F07
0x140018e7c  mov     [rbp+Destination.MaximumLength], dx
0x140018e80  mov     r8b, 2
0x140018e83  movzx   edx, dx
0x140018e86  mov     ecx, 1
0x140018e8b  call    LuafvAllocatePool
0x140018e90  mov     [rbp+Destination.Buffer], rax
0x140018e94  test    rax, rax
0x140018e97  jz      short loc_140018EED
0x140018e99  movzx   ecx, word ptr [rsi+38h]
0x140018e9d  mov     [rbp+Destination.Length], cx
0x140018ea1  mov     r8d, ecx; Size
0x140018ea4  mov     rdx, [rsi+40h]; Src
0x140018ea8  mov     rcx, rax; void *
0x140018eab  call    memmove
0x140018eb0  mov     rdx, rbx; Source
0x140018eb3  lea     rcx, [rbp+Destination]; Destination
0x140018eb7  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018ebe  nop     dword ptr [rax+rax+00h]
0x140018ec3  test    eax, eax
0x140018ec5  js      short loc_140018EE4
0x140018ec7  test    dil, dil
0x140018eca  jz      short loc_140018ED7
0x140018ecc  mov     rcx, [rbx+8]
0x140018ed0  call    LuafvFreePool
0x140018ed5  jmp     short loc_140018EDA
0x140018ed7  mov     dil, 1
0x140018eda  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018ede  movdqu  xmmword ptr [rbx], xmm0
0x140018ee2  jmp     short loc_140018EED
0x140018ee4  mov     rcx, [rbp+Destination.Buffer]
0x140018ee8  call    LuafvFreePool
0x140018eed  mov     rcx, [rbp+Context]; Context
0x140018ef1  call    cs:__imp_FltReleaseContext
0x140018ef8  nop     dword ptr [rax+rax+00h]
0x140018efd  mov     al, dil
0x140018f00  jmp     short loc_140018F09
0x140018f02  call    LuafvFreePool
0x140018f07  xor     al, al
0x140018f09  add     rsp, 48h
0x140018f0d  pop     r15
0x140018f0f  pop     r14
0x140018f11  pop     rdi
0x140018f12  pop     rsi
0x140018f13  pop     rbx
0x140018f14  pop     rbp
0x140018f15  retn
```
