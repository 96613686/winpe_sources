# FltGetInstanceInformation

- ea: `0x180075960`
- end: `0x180075e6d`
- name: `FltGetInstanceInformation`
- size: `1293`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, INSTANCE_INFORMATION_CLASS InformationClass, PVOID Buffer, ULONG BufferSize, PULONG BytesReturned)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180050350`
- `0x180056538`
- `0x180075570`

## callees

- `0x18001ac40`
- `0x180075960`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x180075adc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b89`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075bdd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c8f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075ce7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075d3b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075d8e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075de3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075e31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075adc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b89`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075bdd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c8f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075ce7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075d3b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075d8e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075de3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075e31`

## pseudocode

```c
NTSTATUS __stdcall FltGetInstanceInformation(
        PFLT_INSTANCE Instance,
        INSTANCE_INFORMATION_CLASS InformationClass,
        PVOID Buffer,
        ULONG BufferSize,
        PULONG BytesReturned)
{
  NTSTATUS result; // eax
  _UNICODE_STRING *p_Name; // rbx
  ULONG v9; // r15d
  unsigned __int16 v10; // ax
  __int64 v11; // r13
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // r13
  _UNICODE_STRING *v14; // rdx
  unsigned __int16 v15; // ax
  __int64 v16; // rbx
  _UNICODE_STRING *v17; // rdx
  unsigned __int16 v18; // ax
  __int64 v19; // r13
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // r13
  _UNICODE_STRING *p_DeviceName; // rdx
  unsigned __int16 v23; // ax
  __int64 v24; // rbx
  _UNICODE_STRING *v25; // rdx
  unsigned __int16 Length; // ax
  __int64 v27; // r13
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF

  *BytesReturned = 0;
  DestinationString = 0;
  if ( InformationClass )
  {
    switch ( InformationClass )
    {
      case InstancePartialInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length + 12 + Instance->Name.Length;
        break;
      case InstanceFullInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length
           + Instance->Filter->Name.Length
           + Instance->Volume->DeviceName.Length
           + Instance->Name.Length
           + 20;
        break;
      case InstanceAggregateStandardInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length
           + Instance->Filter->Name.Length
           + Instance->Volume->DeviceName.Length
           + Instance->Name.Length
           + 40;
        break;
      default:
        return -1073741811;
    }
  }
  else
  {
    p_Name = &Instance->Name;
    v9 = Instance->Name.Length + 8;
  }
  if ( BufferSize >= v9 )
  {
    if ( InformationClass )
    {
      if ( InformationClass == InstancePartialInformation )
      {
        *(_DWORD *)Buffer = 0;
        if ( v9 - 12 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 12;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 12);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        Length = p_Name->Length;
        *((_WORD *)Buffer + 2) = p_Name->Length;
        v27 = (unsigned __int16)(Length + 12);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 3) = 12;
        if ( v9 - (unsigned int)v27 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v27;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v27);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        *((_WORD *)Buffer + 4) = Instance->Altitude.Length;
        result = 0;
        *((_WORD *)Buffer + 5) = v27;
      }
      else if ( InformationClass == InstanceFullInformation )
      {
        *(_DWORD *)Buffer = 0;
        if ( v9 - 20 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 20;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 20);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        v18 = p_Name->Length;
        *((_WORD *)Buffer + 2) = p_Name->Length;
        v19 = (unsigned __int16)(v18 + 20);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 3) = 20;
        if ( v9 - (unsigned int)v19 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v19;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v19);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        v20 = Instance->Altitude.Length;
        *((_WORD *)Buffer + 4) = v20;
        *((_WORD *)Buffer + 5) = v19;
        v21 = v20 + v19;
        DestinationString.Length = 0;
        if ( v9 - v21 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v21;
        else
          DestinationString.MaximumLength = -1;
        p_DeviceName = &Instance->Volume->DeviceName;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v21);
        RtlCopyUnicodeString(&DestinationString, p_DeviceName);
        v23 = DestinationString.Length;
        *((_WORD *)Buffer + 6) = DestinationString.Length;
        *((_WORD *)Buffer + 7) = v21;
        v24 = (unsigned __int16)(v23 + v21);
        DestinationString.Length = 0;
        if ( v9 - (unsigned __int16)v24 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v24;
        else
          DestinationString.MaximumLength = -1;
        v25 = &Instance->Filter->Name;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v24);
        RtlCopyUnicodeString(&DestinationString, v25);
        result = 0;
        *((_WORD *)Buffer + 8) = Instance->Filter->Name.Length;
        *((_WORD *)Buffer + 9) = v24;
      }
      else
      {
        *(_DWORD *)Buffer = 0;
        *((_DWORD *)Buffer + 1) = 1;
        *((_DWORD *)Buffer + 3) = Instance->Volume->Frame->FrameID;
        *((_DWORD *)Buffer + 4) = Instance->Volume->FileSystemType;
        *((_DWORD *)Buffer + 2) = 0;
        if ( FltpIsVolumeDetached((__int64)Instance->Volume) )
          *((_DWORD *)Buffer + 2) |= 1u;
        DestinationString.Length = 0;
        if ( v9 - 40 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 40;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 40);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        v10 = p_Name->Length;
        *((_WORD *)Buffer + 10) = p_Name->Length;
        v11 = (unsigned __int16)(v10 + 40);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 11) = 40;
        if ( v9 - (unsigned int)v11 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v11;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v11);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        v12 = Instance->Altitude.Length;
        *((_WORD *)Buffer + 12) = v12;
        *((_WORD *)Buffer + 13) = v11;
        v13 = v12 + v11;
        DestinationString.Length = 0;
        if ( v9 - v13 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v13;
        else
          DestinationString.MaximumLength = -1;
        v14 = &Instance->Volume->DeviceName;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v13);
        RtlCopyUnicodeString(&DestinationString, v14);
        v15 = DestinationString.Length;
        *((_WORD *)Buffer + 14) = DestinationString.Length;
        *((_WORD *)Buffer + 15) = v13;
        v16 = (unsigned __int16)(v15 + v13);
        DestinationString.Length = 0;
        if ( v9 - (unsigned __int16)v16 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v16;
        else
          DestinationString.MaximumLength = -1;
        v17 = &Instance->Filter->Name;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v16);
        RtlCopyUnicodeString(&DestinationString, v17);
        *((_WORD *)Buffer + 16) = Instance->Filter->Name.Length;
        *((_WORD *)Buffer + 17) = v16;
        *((_DWORD *)Buffer + 9) = Instance->SupportedFeatures;
        result = 0;
      }
    }
    else
    {
      *(_DWORD *)Buffer = 0;
      if ( v9 - 8 <= 0xFFFF )
        DestinationString.MaximumLength = v9 - 8;
      else
        DestinationString.MaximumLength = -1;
      DestinationString.Buffer = (wchar_t *)((char *)Buffer + 8);
      RtlCopyUnicodeString(&DestinationString, p_Name);
      *((_WORD *)Buffer + 2) = p_Name->Length;
      result = 0;
      *((_WORD *)Buffer + 3) = 8;
    }
    *BytesReturned = v9;
  }
  else
  {
    *BytesReturned = v9;
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x180075960  mov     [rsp-28h+arg_8], rbx
0x180075965  mov     [rsp-28h+arg_10], rsi
0x18007596a  push    rbp
0x18007596b  push    rdi
0x18007596c  push    r13
0x18007596e  push    r14
0x180075970  push    r15
0x180075972  mov     rbp, rsp
0x180075975  sub     rsp, 30h
0x180075979  mov     rdi, [rbp+BytesReturned]
0x18007597d  xor     r13d, r13d
0x180075980  xorps   xmm0, xmm0
0x180075983  mov     rsi, r8
0x180075986  mov     r10d, edx
0x180075989  mov     r14, rcx
0x18007598c  mov     eax, edx
0x18007598e  mov     [rdi], r13d
0x180075991  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180075995  test    edx, edx
0x180075997  jz      loc_180075A1F
0x18007599d  sub     eax, 1
0x1800759a0  jz      short loc_180075A0A
0x1800759a2  sub     eax, 1
0x1800759a5  jz      short loc_1800759E0
0x1800759a7  cmp     eax, 1
0x1800759aa  jz      short loc_1800759B6
0x1800759ac  mov     eax, 0C000000Dh
0x1800759b1  jmp     loc_180075E55
0x1800759b6  mov     rax, [rcx+40h]
0x1800759ba  lea     rbx, [rcx+68h]
0x1800759be  movzx   r15d, word ptr [rbx]
0x1800759c2  add     r15d, 28h ; '('
0x1800759c6  movzx   edx, word ptr [rax+70h]
0x1800759ca  mov     rax, [rcx+48h]
0x1800759ce  movzx   ecx, word ptr [rax+40h]
0x1800759d2  movzx   eax, word ptr [r14+58h]
0x1800759d7  add     edx, ecx
0x1800759d9  add     edx, eax
0x1800759db  add     r15d, edx
0x1800759de  jmp     short loc_180075A2C
0x1800759e0  mov     rax, [rcx+40h]
0x1800759e4  lea     rbx, [rcx+68h]
0x1800759e8  movzx   r15d, word ptr [rbx]
0x1800759ec  add     r15d, 14h
0x1800759f0  movzx   edx, word ptr [rax+70h]
0x1800759f4  mov     rax, [rcx+48h]
0x1800759f8  movzx   ecx, word ptr [rax+40h]
0x1800759fc  movzx   eax, word ptr [r14+58h]
0x180075a01  add     edx, ecx
0x180075a03  add     edx, eax
0x180075a05  add     r15d, edx
0x180075a08  jmp     short loc_180075A2C
0x180075a0a  movzx   r15d, word ptr [rcx+68h]
0x180075a0f  lea     rbx, [rcx+68h]
0x180075a13  movzx   ecx, word ptr [rcx+58h]
0x180075a17  add     ecx, 0Ch
0x180075a1a  add     r15d, ecx
0x180075a1d  jmp     short loc_180075A2C
0x180075a1f  movzx   r15d, word ptr [rcx+68h]
0x180075a24  lea     rbx, [rcx+68h]
0x180075a28  add     r15d, 8
0x180075a2c  cmp     r9d, r15d
0x180075a2f  jnb     short loc_180075A3E
0x180075a31  mov     [rdi], r15d
0x180075a34  mov     eax, 0C0000023h
0x180075a39  jmp     loc_180075E55
0x180075a3e  mov     [rsp+30h+arg_0], r12
0x180075a43  test    r10d, r10d
0x180075a46  jz      loc_180075E01
0x180075a4c  sub     r10d, 1
0x180075a50  jz      loc_180075D5E
0x180075a56  sub     r10d, 1
0x180075a5a  jz      loc_180075C0A
0x180075a60  cmp     r10d, 1
0x180075a64  jz      short loc_180075A70
0x180075a66  mov     eax, 0C000000Dh
0x180075a6b  jmp     loc_180075E50
0x180075a70  mov     [r8], r13d
0x180075a73  mov     dword ptr [r8+4], 1
0x180075a7b  mov     rax, [r14+40h]
0x180075a7f  mov     rcx, [rax+68h]
0x180075a83  mov     eax, [rcx+18h]
0x180075a86  mov     [r8+0Ch], eax
0x180075a8a  mov     rax, [r14+40h]
0x180075a8e  mov     ecx, [rax+3Ch]
0x180075a91  mov     [r8+10h], ecx
0x180075a95  mov     [r8+8], r13d
0x180075a99  mov     rcx, [r14+40h]
0x180075a9d  call    FltpIsVolumeDetached
0x180075aa2  test    al, al
0x180075aa4  jz      short loc_180075AAA
0x180075aa6  or      dword ptr [rsi+8], 1
0x180075aaa  lea     eax, [r15-28h]
0x180075aae  mov     [rbp+DestinationString.Length], r13w
0x180075ab3  mov     r12d, 0FFFFh
0x180075ab9  cmp     eax, r12d
0x180075abc  jbe     short loc_180075AC5
0x180075abe  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075ac3  jmp     short loc_180075ACD
0x180075ac5  lea     eax, [r15-28h]
0x180075ac9  mov     [rbp+DestinationString.MaximumLength], ax
0x180075acd  lea     rax, [rsi+28h]
0x180075ad1  mov     rdx, rbx; SourceString
0x180075ad4  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075ad8  mov     [rbp+DestinationString.Buffer], rax
0x180075adc  call    cs:__imp_RtlCopyUnicodeString
0x180075ae3  nop     dword ptr [rax+rax+00h]
0x180075ae8  movzx   eax, word ptr [rbx]
0x180075aeb  mov     [rsi+14h], ax
0x180075aef  add     ax, 28h ; '('
0x180075af3  movzx   r13d, ax
0x180075af7  xor     eax, eax
0x180075af9  mov     [rbp+DestinationString.Length], ax
0x180075afd  mov     eax, r15d
0x180075b00  sub     eax, r13d
0x180075b03  mov     word ptr [rsi+16h], 28h ; '('
0x180075b09  cmp     eax, r12d
0x180075b0c  jbe     short loc_180075B15
0x180075b0e  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075b13  jmp     short loc_180075B21
0x180075b15  movzx   eax, r15w
0x180075b19  sub     ax, r13w
0x180075b1d  mov     [rbp+DestinationString.MaximumLength], ax
0x180075b21  lea     rax, [rsi+r13]
0x180075b25  lea     rdx, [r14+58h]; SourceString
0x180075b29  mov     [rbp+DestinationString.Buffer], rax
0x180075b2d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075b31  call    cs:__imp_RtlCopyUnicodeString
0x180075b38  nop     dword ptr [rax+rax+00h]
0x180075b3d  movzx   eax, word ptr [r14+58h]
0x180075b42  mov     [rsi+18h], ax
0x180075b46  mov     [rsi+1Ah], r13w
0x180075b4b  add     r13w, ax
0x180075b4f  xor     eax, eax
0x180075b51  movzx   ebx, r13w
0x180075b55  mov     [rbp+DestinationString.Length], ax
0x180075b59  mov     eax, r15d
0x180075b5c  sub     eax, ebx
0x180075b5e  cmp     eax, r12d
0x180075b61  jbe     short loc_180075B6A
0x180075b63  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075b68  jmp     short loc_180075B75
0x180075b6a  movzx   eax, r15w
0x180075b6e  sub     ax, bx
0x180075b71  mov     [rbp+DestinationString.MaximumLength], ax
0x180075b75  mov     rdx, [r14+40h]
0x180075b79  lea     rax, [rsi+rbx]
0x180075b7d  add     rdx, 70h ; 'p'; SourceString
0x180075b81  mov     [rbp+DestinationString.Buffer], rax
0x180075b85  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075b89  call    cs:__imp_RtlCopyUnicodeString
0x180075b90  nop     dword ptr [rax+rax+00h]
0x180075b95  movzx   eax, [rbp+DestinationString.Length]
0x180075b99  mov     [rsi+1Ch], ax
0x180075b9d  mov     [rsi+1Eh], bx
0x180075ba1  add     bx, ax
0x180075ba4  xor     eax, eax
0x180075ba6  movzx   ebx, bx
0x180075ba9  mov     [rbp+DestinationString.Length], ax
0x180075bad  mov     eax, r15d
0x180075bb0  sub     eax, ebx
0x180075bb2  cmp     eax, r12d
0x180075bb5  jbe     short loc_180075BBE
0x180075bb7  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075bbc  jmp     short loc_180075BC9
0x180075bbe  movzx   eax, r15w
0x180075bc2  sub     ax, bx
0x180075bc5  mov     [rbp+DestinationString.MaximumLength], ax
0x180075bc9  mov     rdx, [r14+48h]
0x180075bcd  lea     rax, [rsi+rbx]
0x180075bd1  add     rdx, 40h ; '@'; SourceString
0x180075bd5  mov     [rbp+DestinationString.Buffer], rax
0x180075bd9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075bdd  call    cs:__imp_RtlCopyUnicodeString
0x180075be4  nop     dword ptr [rax+rax+00h]
0x180075be9  mov     rax, [r14+48h]
0x180075bed  movzx   ecx, word ptr [rax+40h]
0x180075bf1  mov     [rsi+20h], cx
0x180075bf5  mov     [rsi+22h], bx
0x180075bf9  mov     eax, [r14+2C0h]
0x180075c00  mov     [rsi+24h], eax
0x180075c03  xor     eax, eax
0x180075c05  jmp     loc_180075E4D
0x180075c0a  lea     eax, [r15-14h]
0x180075c0e  mov     [r8], r13d
0x180075c11  mov     r12d, 0FFFFh
0x180075c17  cmp     eax, r12d
0x180075c1a  jbe     short loc_180075C23
0x180075c1c  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075c21  jmp     short loc_180075C2B
0x180075c23  lea     eax, [r15-14h]
0x180075c27  mov     [rbp+DestinationString.MaximumLength], ax
0x180075c2b  lea     rax, [r8+14h]
0x180075c2f  mov     rdx, rbx; SourceString
0x180075c32  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075c36  mov     [rbp+DestinationString.Buffer], rax
0x180075c3a  call    cs:__imp_RtlCopyUnicodeString
0x180075c41  nop     dword ptr [rax+rax+00h]
0x180075c46  movzx   eax, word ptr [rbx]
0x180075c49  mov     [rsi+4], ax
0x180075c4d  add     ax, 14h
0x180075c51  movzx   r13d, ax
0x180075c55  xor     eax, eax
0x180075c57  mov     [rbp+DestinationString.Length], ax
0x180075c5b  mov     eax, r15d
0x180075c5e  sub     eax, r13d
0x180075c61  mov     word ptr [rsi+6], 14h
0x180075c67  cmp     eax, r12d
0x180075c6a  jbe     short loc_180075C73
0x180075c6c  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075c71  jmp     short loc_180075C7F
0x180075c73  movzx   eax, r15w
0x180075c77  sub     ax, r13w
0x180075c7b  mov     [rbp+DestinationString.MaximumLength], ax
0x180075c7f  lea     rax, [rsi+r13]
0x180075c83  lea     rdx, [r14+58h]; SourceString
0x180075c87  mov     [rbp+DestinationString.Buffer], rax
0x180075c8b  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075c8f  call    cs:__imp_RtlCopyUnicodeString
0x180075c96  nop     dword ptr [rax+rax+00h]
0x180075c9b  movzx   eax, word ptr [r14+58h]
0x180075ca0  mov     [rsi+8], ax
0x180075ca4  mov     [rsi+0Ah], r13w
0x180075ca9  add     r13w, ax
0x180075cad  xor     eax, eax
0x180075caf  movzx   ebx, r13w
0x180075cb3  mov     [rbp+DestinationString.Length], ax
0x180075cb7  mov     eax, r15d
0x180075cba  sub     eax, ebx
0x180075cbc  cmp     eax, r12d
0x180075cbf  jbe     short loc_180075CC8
0x180075cc1  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075cc6  jmp     short loc_180075CD3
0x180075cc8  movzx   eax, r15w
0x180075ccc  sub     ax, bx
0x180075ccf  mov     [rbp+DestinationString.MaximumLength], ax
0x180075cd3  mov     rdx, [r14+40h]
0x180075cd7  lea     rax, [rsi+rbx]
0x180075cdb  add     rdx, 70h ; 'p'; SourceString
0x180075cdf  mov     [rbp+DestinationString.Buffer], rax
0x180075ce3  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075ce7  call    cs:__imp_RtlCopyUnicodeString
0x180075cee  nop     dword ptr [rax+rax+00h]
0x180075cf3  movzx   eax, [rbp+DestinationString.Length]
0x180075cf7  mov     [rsi+0Ch], ax
0x180075cfb  mov     [rsi+0Eh], bx
0x180075cff  add     bx, ax
0x180075d02  xor     eax, eax
0x180075d04  movzx   ebx, bx
0x180075d07  mov     [rbp+DestinationString.Length], ax
0x180075d0b  mov     eax, r15d
0x180075d0e  sub     eax, ebx
0x180075d10  cmp     eax, r12d
0x180075d13  jbe     short loc_180075D1C
0x180075d15  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075d1a  jmp     short loc_180075D27
0x180075d1c  movzx   eax, r15w
0x180075d20  sub     ax, bx
0x180075d23  mov     [rbp+DestinationString.MaximumLength], ax
0x180075d27  mov     rdx, [r14+48h]
0x180075d2b  lea     rax, [rsi+rbx]
0x180075d2f  add     rdx, 40h ; '@'; SourceString
0x180075d33  mov     [rbp+DestinationString.Buffer], rax
0x180075d37  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075d3b  call    cs:__imp_RtlCopyUnicodeString
0x180075d42  nop     dword ptr [rax+rax+00h]
0x180075d47  mov     rax, [r14+48h]
0x180075d4b  movzx   ecx, word ptr [rax+40h]
0x180075d4f  xor     eax, eax
0x180075d51  mov     [rsi+10h], cx
0x180075d55  mov     [rsi+12h], bx
0x180075d59  jmp     loc_180075E4D
0x180075d5e  lea     eax, [r15-0Ch]
0x180075d62  mov     [r8], r13d
0x180075d65  mov     r12d, 0FFFFh
0x180075d6b  cmp     eax, r12d
0x180075d6e  jbe     short loc_180075D77
0x180075d70  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075d75  jmp     short loc_180075D7F
0x180075d77  lea     eax, [r15-0Ch]
0x180075d7b  mov     [rbp+DestinationString.MaximumLength], ax
0x180075d7f  lea     rax, [r8+0Ch]
0x180075d83  mov     rdx, rbx; SourceString
0x180075d86  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075d8a  mov     [rbp+DestinationString.Buffer], rax
0x180075d8e  call    cs:__imp_RtlCopyUnicodeString
0x180075d95  nop     dword ptr [rax+rax+00h]
0x180075d9a  movzx   eax, word ptr [rbx]
0x180075d9d  mov     [rsi+4], ax
0x180075da1  add     ax, 0Ch
0x180075da5  movzx   r13d, ax
0x180075da9  xor     eax, eax
0x180075dab  mov     [rbp+DestinationString.Length], ax
0x180075daf  mov     eax, r15d
0x180075db2  sub     eax, r13d
0x180075db5  mov     word ptr [rsi+6], 0Ch
0x180075dbb  cmp     eax, r12d
0x180075dbe  jbe     short loc_180075DC7
0x180075dc0  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075dc5  jmp     short loc_180075DD3
  ... truncated ...
```
