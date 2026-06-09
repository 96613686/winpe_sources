# Tcpip4_WSHOpenSocket2

- ea: `0x180017ad0`
- end: `0x180017e01`
- name: `Tcpip4_WSHOpenSocket2`
- size: `817`
- prototype: `__int64 __fastcall(int, int, int, int, int, PUNICODE_STRING DestinationString, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036850`

## callees

- `0x180017ad0`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x180017d7c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180017d7c`
- `ntdll!RtlIntegerToUnicodeString` at `0x180017de7`
- `ntdll!RtlIntegerToUnicodeString` at `0x180017de7`
- `ntdll!RtlAllocateHeap` at `0x180017d55`
- `ntdll!RtlAllocateHeap` at `0x180017d55`
- `ntdll!RtlInitUnicodeString` at `0x180017b7b`
- `ntdll!RtlInitUnicodeString` at `0x180017cb9`
- `ntdll!RtlInitUnicodeString` at `0x180017d09`
- `ntdll!RtlInitUnicodeString` at `0x180017d22`
- `ntdll!RtlInitUnicodeString` at `0x180017b7b`
- `ntdll!RtlInitUnicodeString` at `0x180017cb9`
- `ntdll!RtlInitUnicodeString` at `0x180017d09`
- `ntdll!RtlInitUnicodeString` at `0x180017d22`

## pseudocode

```c
__int64 __fastcall Tcpip4_WSHOpenSocket2(
        _DWORD *a1,
        int *a2,
        _DWORD *a3,
        int a4,
        int a5,
        PUNICODE_STRING DestinationString,
        _QWORD *a7,
        _DWORD *a8)
{
  __int64 v8; // r10
  int v11; // ecx
  char v13; // di
  const wchar_t *v14; // rcx
  __int64 i; // rdx
  __int64 j; // rdx
  unsigned __int16 v18; // ax
  WCHAR *Heap; // rax
  USHORT Length; // r8
  WCHAR *v21; // rcx
  USHORT v22; // ax
  UNICODE_STRING Source; // [rsp+20h] [rbp-38h] BYREF

  v8 = 0;
  v11 = *a2;
  while ( (unsigned int)v8 < 3 )
  {
    if ( *a1 == Tcpip4_TcpMappingTriples[3 * v8]
      && v11 == dword_18005AFF4[3 * v8]
      && (*a3 == dword_18005AFF8[3 * v8] || v11 == 3) )
    {
      if ( (a5 & 0xFFFFFFFE) != 0 )
        return 10022;
      v13 = Tcpip4_TdiModeStream;
      v14 = L"\\Device\\Tcp";
      *a1 = 2;
      *a2 = 1;
      *a3 = 6;
LABEL_9:
      RtlInitUnicodeString(DestinationString, (PCWSTR)((unsigned __int64)v14 & -(__int64)(v13 != 0)));
LABEL_10:
      *a7 = *(unsigned __int16 *)a1;
      *a8 = v13 == 0 ? 0xE0000000 : 0;
      return 0;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 3 )
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= 2 )
          return 10022;
        if ( *a1 == Tcpip4_RawMappingTriples[3 * j]
          && v11 == dword_18005AFB4[3 * j]
          && (*a3 == dword_18005AFB8[3 * j] || v11 == 3) )
        {
          break;
        }
      }
      if ( (a5 & 0xFFFFFFEA) != 0 || *a3 > 0xFFu )
        return 10022;
      v13 = Tcpip4_TdiModeRaw;
      if ( Tcpip4_TdiModeRaw )
      {
        Source = 0;
        RtlInitUnicodeString(&Source, L"\\Device\\RawIp");
        RtlInitUnicodeString(DestinationString, 0);
        v18 = Source.Length + 10;
        DestinationString->MaximumLength = Source.Length + 10;
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        DestinationString->Buffer = Heap;
        if ( !Heap )
          return 10055;
        RtlAppendUnicodeStringToString(DestinationString, &Source);
        DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1] = 92;
        DestinationString->Length += 2;
        DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1] = 0;
        Length = DestinationString->Length;
        v21 = &DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1];
        Source.Length = 0;
        v22 = DestinationString->MaximumLength - Length;
        Source.Buffer = v21;
        LODWORD(v21) = *a3;
        Source.MaximumLength = v22;
        RtlIntegerToUnicodeString((ULONG)v21, 0xAu, &Source);
        DestinationString->Length += Source.Length;
      }
      else
      {
        RtlInitUnicodeString(DestinationString, 0);
      }
      *a1 = 2;
      *a2 = 3;
      goto LABEL_10;
    }
    if ( *a1 == Tcpip4_UdpMappingTriples[3 * i]
      && v11 == dword_18005AFCC[3 * i]
      && (*a3 == dword_18005AFD0[3 * i] || v11 == 3) )
    {
      break;
    }
  }
  if ( (a5 & 0xFFFFFFEA) == 0 && a4 != 2 )
  {
    v13 = Tcpip4_TdiModeDgram;
    v14 = L"\\Device\\Udp";
    *a1 = 2;
    *a2 = 2;
    *a3 = 17;
    goto LABEL_9;
  }
  return 10022;
}

```

## disassembly

```asm
0x180017ad0  mov     [rsp+arg_0], rbx
0x180017ad5  mov     [rsp+arg_10], rbp
0x180017ada  push    rsi
0x180017adb  push    rdi
0x180017adc  push    r13
0x180017ade  push    r14
0x180017ae0  push    r15
0x180017ae2  sub     rsp, 30h
0x180017ae6  xor     r10d, r10d
0x180017ae9  lea     r11, __ImageBase
0x180017af0  mov     rsi, rcx
0x180017af3  mov     r14, r8
0x180017af6  mov     ecx, [rdx]
0x180017af8  mov     r15, rdx
0x180017afb  lea     ebp, [r10+1]
0x180017aff  cmp     r10d, 3
0x180017b03  jnb     loc_180017CE4
0x180017b09  lea     rdx, [r10+r10*2]
0x180017b0d  mov     eax, ds:rva Tcpip4_TcpMappingTriples[r11+rdx*4]
0x180017b15  cmp     [rsi], eax
0x180017b17  jnz     short loc_180017B23
0x180017b19  cmp     ecx, ds:rva dword_18005AFF4[r11+rdx*4]
0x180017b21  jz      short loc_180017B28
0x180017b23  add     r10d, ebp
0x180017b26  jmp     short loc_180017AFF
0x180017b28  mov     eax, ds:rva dword_18005AFF8[r11+rdx*4]
0x180017b30  cmp     [r8], eax
0x180017b33  jnz     loc_180017BD9
0x180017b39  test    [rsp+58h+arg_20], 0FFFFFFFEh
0x180017b44  jnz     loc_180017CDA
0x180017b4a  mov     dil, cs:Tcpip4_TdiModeStream
0x180017b51  lea     rcx, aDeviceTcp; "\\Device\\Tcp"
0x180017b58  mov     dword ptr [rsi], 2
0x180017b5e  mov     [r15], ebp
0x180017b61  mov     dword ptr [r8], 6
0x180017b68  mov     al, dil
0x180017b6b  neg     al
0x180017b6d  sbb     rdx, rdx
0x180017b70  and     rdx, rcx; SourceString
0x180017b73  mov     rcx, [rsp+58h+DestinationString]; DestinationString
0x180017b7b  call    cs:__imp_RtlInitUnicodeString
0x180017b82  nop     dword ptr [rax+rax+00h]
0x180017b87  movzx   eax, word ptr [rsi]
0x180017b8a  neg     dil
0x180017b8d  mov     rcx, [rsp+58h+arg_30]
0x180017b95  mov     [rsp+58h+arg_8], 0
0x180017b9e  mov     word ptr [rsp+58h+arg_8], ax
0x180017ba3  mov     rax, [rsp+58h+arg_8]
0x180017ba8  mov     [rcx], rax
0x180017bab  sbb     ecx, ecx
0x180017bad  mov     rax, [rsp+58h+arg_38]
0x180017bb5  not     ecx
0x180017bb7  and     ecx, 0E0000000h
0x180017bbd  mov     [rax], ecx
0x180017bbf  xor     eax, eax
0x180017bc1  mov     rbx, [rsp+58h+arg_0]
0x180017bc6  mov     rbp, [rsp+58h+arg_10]
0x180017bcb  add     rsp, 30h
0x180017bcf  pop     r15
0x180017bd1  pop     r14
0x180017bd3  pop     r13
0x180017bd5  pop     rdi
0x180017bd6  pop     rsi
0x180017bd7  retn
0x180017bd9  cmp     ecx, 3
0x180017bdc  jnz     loc_180017B23
0x180017be2  jmp     loc_180017B39
0x180017be7  cmp     edx, 3
0x180017bea  jnb     loc_180017CEB
0x180017bf0  lea     r8, [rdx+rdx*2]
0x180017bf4  mov     eax, ds:rva Tcpip4_UdpMappingTriples[r11+r8*4]
0x180017bfc  cmp     [rsi], eax
0x180017bfe  jnz     short loc_180017C0A
0x180017c00  cmp     ecx, ds:rva dword_18005AFCC[r11+r8*4]
0x180017c08  jz      short loc_180017C0E
0x180017c0a  add     edx, ebp
0x180017c0c  jmp     short loc_180017BE7
0x180017c0e  mov     eax, ds:rva dword_18005AFD0[r11+r8*4]
0x180017c16  cmp     [r14], eax
0x180017c19  jnz     short loc_180017C59
0x180017c1b  test    [rsp+58h+arg_20], 0FFFFFFEAh
0x180017c26  jnz     loc_180017CDA
0x180017c2c  mov     ebx, 2
0x180017c31  cmp     r9d, ebx
0x180017c34  jz      loc_180017CDA
0x180017c3a  mov     dil, cs:Tcpip4_TdiModeDgram
0x180017c41  lea     rcx, aDeviceUdp; "\\Device\\Udp"
0x180017c48  mov     [rsi], ebx
0x180017c4a  mov     [r15], ebx
0x180017c4d  mov     dword ptr [r14], 11h
0x180017c54  jmp     loc_180017B68
0x180017c59  cmp     ecx, 3
0x180017c5c  jnz     short loc_180017C0A
0x180017c5e  jmp     short loc_180017C1B
0x180017c60  cmp     edx, ebx
0x180017c62  jnb     short loc_180017CDA
0x180017c64  lea     r8, [rdx+rdx*2]
0x180017c68  mov     eax, ds:rva Tcpip4_RawMappingTriples[r11+r8*4]
0x180017c70  cmp     [rsi], eax
0x180017c72  jnz     short loc_180017C7E
0x180017c74  cmp     ecx, ds:rva dword_18005AFB4[r11+r8*4]
0x180017c7c  jz      short loc_180017C82
0x180017c7e  add     edx, ebp
0x180017c80  jmp     short loc_180017C60
0x180017c82  mov     eax, [r14]
0x180017c85  cmp     eax, ds:rva dword_18005AFB8[r11+r8*4]
0x180017c8d  jnz     short loc_180017CD3
0x180017c8f  test    [rsp+58h+arg_20], 0FFFFFFEAh
0x180017c9a  jnz     short loc_180017CDA
0x180017c9c  cmp     eax, 0FFh
0x180017ca1  ja      short loc_180017CDA
0x180017ca3  mov     dil, cs:Tcpip4_TdiModeRaw
0x180017caa  test    dil, dil
0x180017cad  jnz     short loc_180017CF5
0x180017caf  mov     rcx, [rsp+58h+DestinationString]; DestinationString
0x180017cb7  xor     edx, edx; SourceString
0x180017cb9  call    cs:__imp_RtlInitUnicodeString
0x180017cc0  nop     dword ptr [rax+rax+00h]
0x180017cc5  mov     [rsi], ebx
0x180017cc7  mov     dword ptr [r15], 3
0x180017cce  jmp     loc_180017B87
0x180017cd3  cmp     ecx, 3
0x180017cd6  jnz     short loc_180017C7E
0x180017cd8  jmp     short loc_180017C8F
0x180017cda  mov     eax, 2726h
0x180017cdf  jmp     loc_180017BC1
0x180017ce4  xor     edx, edx
0x180017ce6  jmp     loc_180017BE7
0x180017ceb  xor     edx, edx
0x180017ced  lea     ebx, [rdx+2]
0x180017cf0  jmp     loc_180017C60
0x180017cf5  xorps   xmm0, xmm0
0x180017cf8  lea     rdx, aDeviceRawip; "\\Device\\RawIp"
0x180017cff  lea     rcx, [rsp+58h+Source]; DestinationString
0x180017d04  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x180017d09  call    cs:__imp_RtlInitUnicodeString
0x180017d10  nop     dword ptr [rax+rax+00h]
0x180017d15  mov     rbp, [rsp+58h+DestinationString]
0x180017d1d  xor     edx, edx; SourceString
0x180017d1f  mov     rcx, rbp; DestinationString
0x180017d22  call    cs:__imp_RtlInitUnicodeString
0x180017d29  nop     dword ptr [rax+rax+00h]
0x180017d2e  movzx   eax, [rsp+58h+Source.Length]
0x180017d33  mov     r13d, 0Ah
0x180017d39  add     ax, r13w
0x180017d3d  xor     edx, edx; Flags
0x180017d3f  movzx   r8d, ax; Size
0x180017d43  mov     [rbp+2], r8w
0x180017d48  mov     rcx, gs:60h
0x180017d51  mov     rcx, [rcx+30h]; HeapHandle
0x180017d55  call    cs:__imp_RtlAllocateHeap
0x180017d5c  nop     dword ptr [rax+rax+00h]
0x180017d61  mov     [rbp+8], rax
0x180017d65  test    rax, rax
0x180017d68  jnz     short loc_180017D74
0x180017d6a  mov     eax, 2747h
0x180017d6f  jmp     loc_180017BC1
0x180017d74  lea     rdx, [rsp+58h+Source]; Source
0x180017d79  mov     rcx, rbp; Destination
0x180017d7c  call    cs:__imp_RtlAppendUnicodeStringToString
0x180017d83  nop     dword ptr [rax+rax+00h]
0x180017d88  movzx   ecx, word ptr [rbp+0]
0x180017d8c  mov     edx, r13d; Base
0x180017d8f  mov     rax, [rbp+8]
0x180017d93  shr     rcx, 1
0x180017d96  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180017d9c  xor     eax, eax
0x180017d9e  add     [rbp+0], bx
0x180017da2  movzx   r8d, word ptr [rbp+0]
0x180017da7  mov     rcx, [rbp+8]
0x180017dab  shr     r8, 1
0x180017dae  mov     [rcx+r8*2], ax
0x180017db3  movzx   r8d, word ptr [rbp+0]
0x180017db8  mov     rax, [rbp+8]
0x180017dbc  mov     ecx, r8d
0x180017dbf  shr     rcx, 1
0x180017dc2  lea     rcx, [rax+rcx*2]
0x180017dc6  xor     eax, eax
0x180017dc8  mov     [rsp+58h+Source.Length], ax
0x180017dcd  movzx   eax, word ptr [rbp+2]
0x180017dd1  sub     ax, r8w
0x180017dd5  mov     [rsp+58h+Source.Buffer], rcx
0x180017dda  mov     ecx, [r14]; Value
0x180017ddd  lea     r8, [rsp+58h+Source]; String
0x180017de2  mov     [rsp+58h+Source.MaximumLength], ax
0x180017de7  call    cs:__imp_RtlIntegerToUnicodeString
0x180017dee  nop     dword ptr [rax+rax+00h]
0x180017df3  movzx   eax, [rsp+58h+Source.Length]
0x180017df8  add     [rbp+0], ax
0x180017dfc  jmp     loc_180017CC5
```
