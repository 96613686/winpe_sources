# LuafvSupplyFullPath

- ea: `0x140018ce8`
- end: `0x140018f67`
- name: `LuafvSupplyFullPath`
- size: `639`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001897c`
- `0x140023d14`

## callees

- `0x140006080`
- `0x140018ce8`
- `0x140019780`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018e70`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018e70`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018df2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018f07`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018df2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018f07`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018ddf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140018ddf`
- `FLTMGR!FltReleaseContext` at `0x140018ebb`
- `FLTMGR!FltReleaseContext` at `0x140018f41`
- `FLTMGR!FltReleaseContext` at `0x140018ebb`
- `FLTMGR!FltReleaseContext` at `0x140018f41`
- `FLTMGR!FltGetInstanceContext` at `0x140018e90`
- `FLTMGR!FltGetInstanceContext` at `0x140018e90`

## pseudocode

```c
char __fastcall LuafvSupplyFullPath(__int64 a1, __int64 a2)
{
  char v2; // di
  bool v3; // cf
  __int64 v6; // rcx
  struct _FILE_OBJECT *v7; // rdx
  unsigned int v8; // esi
  const void *v9; // r14
  char *Pool; // rax
  __int64 v11; // rsi
  unsigned __int16 v12; // dx
  char *v13; // rax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+30h] [rbp-18h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+40h] BYREF

  v2 = 0;
  Context = 0;
  v3 = *(_WORD *)a2 < 2u;
  *(_OWORD *)Src = 0;
  Destination = 0;
  if ( !v3 && **(_WORD **)(a2 + 8) == 92 )
    goto LABEL_21;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(struct _FILE_OBJECT **)(v6 + 8);
  if ( v7->RelatedFileObject && !*(_BYTE *)(v6 + 4) )
  {
    if ( (int)LuafvGetNameFileObject(*(PFLT_INSTANCE *)(v6 + 16), v7->RelatedFileObject, Src) < 0 )
      return 0;
    v8 = LOWORD(Src[0]);
    v9 = Src[1];
    if ( LOWORD(Src[0]) >= 2u && *(_WORD *)Src[1] == 92 && LOWORD(Src[0]) <= 0x1000u )
    {
      Destination.MaximumLength = *(_WORD *)a2 + LOWORD(Src[0]) + 2;
      Pool = LuafvAllocatePool(1, Destination.MaximumLength, 2);
      Destination.Buffer = (PWSTR)Pool;
      if ( Pool )
      {
        Destination.Length = v8;
        memmove(Pool, v9, v8);
        if ( Destination.Buffer[((unsigned __int64)(unsigned __int16)v8 >> 1) - 1] != 92 )
          RtlAppendUnicodeToString(&Destination, L"\\");
        if ( RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)a2) < 0 )
        {
          LuafvFreePool((__int64)Destination.Buffer);
        }
        else
        {
          v2 = 1;
          *(struct _UNICODE_STRING *)a2 = Destination;
        }
      }
    }
    LuafvFreePool((__int64)v9);
    if ( !v2 )
      return 0;
    goto LABEL_21;
  }
  if ( (int)LuafvGetNameFileObject(*(PFLT_INSTANCE *)(v6 + 16), v7, &Destination) >= 0 )
  {
    if ( Destination.Length < 2u || *Destination.Buffer != 92 )
    {
      LuafvFreePool((__int64)Destination.Buffer);
      return 0;
    }
    v2 = 1;
    *(struct _UNICODE_STRING *)a2 = Destination;
LABEL_21:
    if ( !RtlPrefixUnicodeString(&LuafvDeviceNamePrefix, (PCUNICODE_STRING)a2, 1u)
      && FltGetInstanceContext(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL), &Context) >= 0 )
    {
      v11 = *((_QWORD *)Context + 3);
      v12 = *(_WORD *)(v11 + 56) + *(_WORD *)a2;
      if ( v12 < *(_WORD *)a2 )
      {
        FltReleaseContext(Context);
        return 0;
      }
      Destination.MaximumLength = *(_WORD *)(v11 + 56) + *(_WORD *)a2;
      v13 = LuafvAllocatePool(1, v12, 2);
      Destination.Buffer = (PWSTR)v13;
      if ( v13 )
      {
        Destination.Length = *(_WORD *)(v11 + 56);
        memmove(v13, *(const void **)(v11 + 64), Destination.Length);
        if ( RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)a2) < 0 )
        {
          LuafvFreePool((__int64)Destination.Buffer);
        }
        else
        {
          if ( v2 )
            LuafvFreePool(*(_QWORD *)(a2 + 8));
          else
            v2 = 1;
          *(struct _UNICODE_STRING *)a2 = Destination;
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
0x140018ce8  push    rbp
0x140018cea  push    rbx
0x140018ceb  push    rsi
0x140018cec  push    rdi
0x140018ced  push    r14
0x140018cef  push    r15
0x140018cf1  mov     rbp, rsp
0x140018cf4  sub     rsp, 48h
0x140018cf8  xor     dil, dil
0x140018cfb  mov     [rbp+Context], 0
0x140018d03  cmp     word ptr [rdx], 2
0x140018d07  xorps   xmm0, xmm0
0x140018d0a  xorps   xmm1, xmm1
0x140018d0d  mov     rbx, rdx
0x140018d10  mov     r15, rcx
0x140018d13  movups  xmmword ptr [rbp+Src], xmm0
0x140018d17  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x140018d1b  jb      short loc_140018D2B
0x140018d1d  mov     rax, [rdx+8]
0x140018d21  cmp     word ptr [rax], 5Ch ; '\'
0x140018d25  jz      loc_140018E63
0x140018d2b  mov     rcx, [rcx+10h]
0x140018d2f  mov     rdx, [rcx+8]; FileObject
0x140018d33  mov     rax, [rdx+40h]
0x140018d37  test    rax, rax
0x140018d3a  jz      loc_140018E2A
0x140018d40  cmp     [rcx+4], dil
0x140018d44  jnz     loc_140018E2A
0x140018d4a  mov     rcx, [rcx+10h]; Instance
0x140018d4e  lea     r8, [rbp+Src]
0x140018d52  mov     rdx, rax; FileObject
0x140018d55  call    LuafvGetNameFileObject
0x140018d5a  test    eax, eax
0x140018d5c  js      loc_140018F57
0x140018d62  movzx   esi, word ptr [rbp+Src]
0x140018d66  mov     r14, [rbp+Src+8]
0x140018d6a  cmp     esi, 2
0x140018d6d  jb      loc_140018E18
0x140018d73  cmp     word ptr [r14], 5Ch ; '\'
0x140018d78  jnz     loc_140018E18
0x140018d7e  mov     eax, 1000h
0x140018d83  cmp     si, ax
0x140018d86  ja      loc_140018E18
0x140018d8c  lea     eax, [rsi+2]
0x140018d8f  mov     r8b, 2
0x140018d92  add     ax, [rbx]
0x140018d95  mov     ecx, 1
0x140018d9a  movzx   edx, ax
0x140018d9d  mov     [rbp+Destination.MaximumLength], dx
0x140018da1  call    LuafvAllocatePool
0x140018da6  mov     [rbp+Destination.Buffer], rax
0x140018daa  test    rax, rax
0x140018dad  jz      short loc_140018E18
0x140018daf  mov     r8d, esi; Size
0x140018db2  mov     [rbp+Destination.Length], si
0x140018db6  mov     rdx, r14; Src
0x140018db9  mov     rcx, rax; void *
0x140018dbc  call    memmove
0x140018dc1  movzx   ecx, [rbp+Destination.Length]
0x140018dc5  mov     rax, [rbp+Destination.Buffer]
0x140018dc9  shr     rcx, 1
0x140018dcc  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140018dd2  jz      short loc_140018DEB
0x140018dd4  lea     rdx, Source; "\\"
0x140018ddb  lea     rcx, [rbp+Destination]; Destination
0x140018ddf  call    cs:__imp_RtlAppendUnicodeToString
0x140018de6  nop     dword ptr [rax+rax+00h]
0x140018deb  mov     rdx, rbx; Source
0x140018dee  lea     rcx, [rbp+Destination]; Destination
0x140018df2  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018df9  nop     dword ptr [rax+rax+00h]
0x140018dfe  test    eax, eax
0x140018e00  js      short loc_140018E0F
0x140018e02  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018e06  mov     dil, 1
0x140018e09  movdqu  xmmword ptr [rbx], xmm0
0x140018e0d  jmp     short loc_140018E18
0x140018e0f  mov     rcx, [rbp+Destination.Buffer]
0x140018e13  call    LuafvFreePool
0x140018e18  mov     rcx, r14
0x140018e1b  call    LuafvFreePool
0x140018e20  test    dil, dil
0x140018e23  jnz     short loc_140018E63
0x140018e25  jmp     loc_140018F57
0x140018e2a  mov     rcx, [rcx+10h]; Instance
0x140018e2e  lea     r8, [rbp+Destination]
0x140018e32  call    LuafvGetNameFileObject
0x140018e37  test    eax, eax
0x140018e39  js      loc_140018F57
0x140018e3f  cmp     [rbp+Destination.Length], 2
0x140018e44  mov     rcx, [rbp+Destination.Buffer]
0x140018e48  jb      loc_140018F52
0x140018e4e  cmp     word ptr [rcx], 5Ch ; '\'
0x140018e52  jnz     loc_140018F52
0x140018e58  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018e5c  mov     dil, 1
0x140018e5f  movdqu  xmmword ptr [rbx], xmm0
0x140018e63  mov     r8b, 1; CaseInSensitive
0x140018e66  lea     rcx, LuafvDeviceNamePrefix; String1
0x140018e6d  mov     rdx, rbx; String2
0x140018e70  call    cs:__imp_RtlPrefixUnicodeString
0x140018e77  nop     dword ptr [rax+rax+00h]
0x140018e7c  test    al, al
0x140018e7e  jnz     loc_140018F4D
0x140018e84  mov     rcx, [r15+10h]
0x140018e88  lea     rdx, [rbp+Context]; Context
0x140018e8c  mov     rcx, [rcx+10h]; Instance
0x140018e90  call    cs:__imp_FltGetInstanceContext
0x140018e97  nop     dword ptr [rax+rax+00h]
0x140018e9c  test    eax, eax
0x140018e9e  js      loc_140018F4D
0x140018ea4  movzx   eax, word ptr [rbx]
0x140018ea7  mov     rcx, [rbp+Context]; Context
0x140018eab  movzx   edx, ax
0x140018eae  mov     rsi, [rcx+18h]
0x140018eb2  add     dx, [rsi+38h]
0x140018eb6  cmp     dx, ax
0x140018eb9  jnb     short loc_140018ECC
0x140018ebb  call    cs:__imp_FltReleaseContext
0x140018ec2  nop     dword ptr [rax+rax+00h]
0x140018ec7  jmp     loc_140018F57
0x140018ecc  mov     [rbp+Destination.MaximumLength], dx
0x140018ed0  mov     r8b, 2
0x140018ed3  movzx   edx, dx
0x140018ed6  mov     ecx, 1
0x140018edb  call    LuafvAllocatePool
0x140018ee0  mov     [rbp+Destination.Buffer], rax
0x140018ee4  test    rax, rax
0x140018ee7  jz      short loc_140018F3D
0x140018ee9  movzx   ecx, word ptr [rsi+38h]
0x140018eed  mov     [rbp+Destination.Length], cx
0x140018ef1  mov     r8d, ecx; Size
0x140018ef4  mov     rdx, [rsi+40h]; Src
0x140018ef8  mov     rcx, rax; void *
0x140018efb  call    memmove
0x140018f00  mov     rdx, rbx; Source
0x140018f03  lea     rcx, [rbp+Destination]; Destination
0x140018f07  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018f0e  nop     dword ptr [rax+rax+00h]
0x140018f13  test    eax, eax
0x140018f15  js      short loc_140018F34
0x140018f17  test    dil, dil
0x140018f1a  jz      short loc_140018F27
0x140018f1c  mov     rcx, [rbx+8]
0x140018f20  call    LuafvFreePool
0x140018f25  jmp     short loc_140018F2A
0x140018f27  mov     dil, 1
0x140018f2a  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x140018f2e  movdqu  xmmword ptr [rbx], xmm0
0x140018f32  jmp     short loc_140018F3D
0x140018f34  mov     rcx, [rbp+Destination.Buffer]
0x140018f38  call    LuafvFreePool
0x140018f3d  mov     rcx, [rbp+Context]; Context
0x140018f41  call    cs:__imp_FltReleaseContext
0x140018f48  nop     dword ptr [rax+rax+00h]
0x140018f4d  mov     al, dil
0x140018f50  jmp     short loc_140018F59
0x140018f52  call    LuafvFreePool
0x140018f57  xor     al, al
0x140018f59  add     rsp, 48h
0x140018f5d  pop     r15
0x140018f5f  pop     r14
0x140018f61  pop     rdi
0x140018f62  pop     rsi
0x140018f63  pop     rbx
0x140018f64  pop     rbp
0x140018f65  retn
```
