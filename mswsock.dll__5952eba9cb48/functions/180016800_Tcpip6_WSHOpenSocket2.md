# Tcpip6_WSHOpenSocket2

- ea: `0x180016800`
- end: `0x180016b21`
- name: `Tcpip6_WSHOpenSocket2`
- size: `801`
- prototype: `__int64 __fastcall(int, int, int, int, int, PUNICODE_STRING DestinationString, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036c90`

## callees

- `0x180016800`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x180016a73`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180016a73`
- `ntdll!RtlIntegerToUnicodeString` at `0x180016adb`
- `ntdll!RtlIntegerToUnicodeString` at `0x180016adb`
- `ntdll!RtlAllocateHeap` at `0x180016a3e`
- `ntdll!RtlAllocateHeap` at `0x180016a3e`
- `ntdll!RtlInitUnicodeString` at `0x1800168a2`
- `ntdll!RtlInitUnicodeString` at `0x1800169fb`
- `ntdll!RtlInitUnicodeString` at `0x180016a11`
- `ntdll!RtlInitUnicodeString` at `0x180016af9`
- `ntdll!RtlInitUnicodeString` at `0x1800168a2`
- `ntdll!RtlInitUnicodeString` at `0x1800169fb`
- `ntdll!RtlInitUnicodeString` at `0x180016a11`
- `ntdll!RtlInitUnicodeString` at `0x180016af9`

## pseudocode

```c
__int64 __fastcall Tcpip6_WSHOpenSocket2(
        _DWORD *a1,
        int *a2,
        _DWORD *a3,
        int a4,
        int a5,
        PUNICODE_STRING DestinationString,
        _QWORD *a7,
        int *a8)
{
  int v8; // r11d
  __int64 i; // r10
  char v13; // di
  const WCHAR *v14; // rdx
  int v15; // ecx
  __int64 j; // rdx
  __int64 k; // rdx
  unsigned __int16 v19; // ax
  WCHAR *Heap; // rax
  USHORT Length; // dx
  WCHAR *v22; // rcx
  USHORT v23; // ax
  UNICODE_STRING Source; // [rsp+20h] [rbp-28h] BYREF

  v8 = *a2;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 3 )
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= 3 )
        {
          for ( k = 0; (unsigned int)k < 2; k = (unsigned int)(k + 1) )
          {
            if ( *a1 == Tcpip6_RawMappingTriples[3 * k]
              && v8 == dword_18005B094[3 * k]
              && (*a3 == dword_18005B098[3 * k] || v8 == 3) )
            {
              if ( (a5 & 0xFFFFFFEA) != 0 || *a3 > 0xFFu )
                return 10022;
              v13 = Tcpip6_TdiModeRaw;
              if ( Tcpip6_TdiModeRaw )
              {
                Source = 0;
                RtlInitUnicodeString(&Source, L"\\Device\\RawIp6");
                RtlInitUnicodeString(DestinationString, 0);
                v19 = Source.Length + 10;
                DestinationString->MaximumLength = Source.Length + 10;
                Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
                DestinationString->Buffer = Heap;
                if ( !Heap )
                  return 10055;
                RtlAppendUnicodeStringToString(DestinationString, &Source);
                DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1] = 92;
                DestinationString->Length += 2;
                DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1] = 0;
                Length = DestinationString->Length;
                v22 = &DestinationString->Buffer[(unsigned __int64)DestinationString->Length >> 1];
                Source.Length = 0;
                v23 = DestinationString->MaximumLength - Length;
                Source.Buffer = v22;
                LODWORD(v22) = *a3;
                Source.MaximumLength = v23;
                RtlIntegerToUnicodeString((ULONG)v22, 0xAu, &Source);
                DestinationString->Length += Source.Length;
              }
              else
              {
                RtlInitUnicodeString(DestinationString, 0);
              }
              *a1 = 23;
              *a2 = 3;
              goto LABEL_11;
            }
          }
          return 10022;
        }
        if ( *a1 == Tcpip6_UdpMappingTriples[3 * j]
          && v8 == dword_18005B06C[3 * j]
          && (*a3 == dword_18005B070[3 * j] || v8 == 3) )
        {
          break;
        }
      }
      if ( (a5 & 0xFFFFFFEA) == 0 && a4 != 2 )
      {
        v13 = Tcpip6_TdiModeDgram;
        v14 = L"\\Device\\Udp6";
        *a1 = 23;
        *a2 = 2;
        *a3 = 17;
        goto LABEL_8;
      }
      return 10022;
    }
    if ( *a1 == Tcpip6_TcpMappingTriples[3 * i]
      && v8 == dword_18005B814[3 * i]
      && (*a3 == dword_18005B818[3 * i] || v8 == 3) )
    {
      break;
    }
  }
  if ( (a5 & 0xFFFFFFFE) != 0 )
    return 10022;
  v13 = Tcpip6_TdiModeStream;
  v14 = L"\\Device\\Tcp6";
  *a1 = 23;
  *a2 = 1;
  *a3 = 6;
LABEL_8:
  if ( !v13 )
    v14 = 0;
  RtlInitUnicodeString(DestinationString, v14);
LABEL_11:
  *a7 = *(unsigned __int16 *)a1;
  v15 = 0;
  if ( !v13 )
    v15 = -536870912;
  *a8 = v15;
  return 0;
}

```

## disassembly

```asm
0x180016800  push    rbx
0x180016802  push    rsi
0x180016803  push    r14
0x180016805  sub     rsp, 30h
0x180016809  mov     r11d, [rdx]
0x18001680c  mov     rsi, r8
0x18001680f  mov     [rsp+48h+arg_0], rbp
0x180016814  lea     r8, __ImageBase
0x18001681b  mov     [rsp+48h+arg_10], rdi
0x180016820  mov     r14, rdx
0x180016823  mov     rbx, rcx
0x180016826  xor     r10d, r10d
0x180016829  cmp     r10d, 3
0x18001682d  jnb     loc_180016A5D
0x180016833  lea     rdx, [r10+r10*2]
0x180016837  mov     eax, ds:rva Tcpip6_TcpMappingTriples[r8+rdx*4]
0x18001683f  cmp     [rcx], eax
0x180016841  jnz     loc_180016906
0x180016847  cmp     r11d, ds:rva dword_18005B814[r8+rdx*4]
0x18001684f  jnz     loc_180016906
0x180016855  mov     eax, ds:rva dword_18005B818[r8+rdx*4]
0x18001685d  cmp     [rsi], eax
0x18001685f  jnz     loc_1800168FC
0x180016865  test    [rsp+48h+arg_20], 0FFFFFFFEh
0x18001686d  jnz     loc_180016B17
0x180016873  movzx   edi, cs:Tcpip6_TdiModeStream
0x18001687a  lea     rdx, aDeviceTcp6; "\\Device\\Tcp6"
0x180016881  mov     dword ptr [rcx], 17h
0x180016887  mov     dword ptr [r14], 1
0x18001688e  mov     dword ptr [rsi], 6
0x180016894  mov     rcx, [rsp+48h+DestinationString]; DestinationString
0x180016899  xor     eax, eax
0x18001689b  test    dil, dil
0x18001689e  cmovz   rdx, rax; SourceString
0x1800168a2  call    cs:__imp_RtlInitUnicodeString
0x1800168a9  nop     dword ptr [rax+rax+00h]
0x1800168ae  movzx   eax, word ptr [rbx]
0x1800168b1  mov     rcx, [rsp+48h+arg_30]
0x1800168b9  mov     [rsp+48h+arg_8], 0
0x1800168c2  mov     word ptr [rsp+48h+arg_8], ax
0x1800168c7  mov     rax, [rsp+48h+arg_8]
0x1800168cc  mov     [rcx], rax
0x1800168cf  xor     ecx, ecx
0x1800168d1  test    dil, dil
0x1800168d4  mov     eax, 0E0000000h
0x1800168d9  cmovz   ecx, eax
0x1800168dc  mov     rax, [rsp+48h+arg_38]
0x1800168e4  mov     [rax], ecx
0x1800168e6  xor     eax, eax
0x1800168e8  mov     rdi, [rsp+48h+arg_10]
0x1800168ed  mov     rbp, [rsp+48h+arg_0]
0x1800168f2  add     rsp, 30h
0x1800168f6  pop     r14
0x1800168f8  pop     rsi
0x1800168f9  pop     rbx
0x1800168fa  retn
0x1800168fc  cmp     r11d, 3
0x180016900  jz      loc_180016865
0x180016906  inc     r10d
0x180016909  jmp     loc_180016829
0x180016910  cmp     edx, 3
0x180016913  jnb     loc_180016A64
0x180016919  lea     rcx, [rdx+rdx*2]
0x18001691d  mov     eax, ds:rva Tcpip6_UdpMappingTriples[r8+rcx*4]
0x180016925  cmp     [rbx], eax
0x180016927  jnz     short loc_180016983
0x180016929  cmp     r11d, ds:rva dword_18005B06C[r8+rcx*4]
0x180016931  jnz     short loc_180016983
0x180016933  mov     eax, ds:rva dword_18005B070[r8+rcx*4]
0x18001693b  cmp     [rsi], eax
0x18001693d  jnz     short loc_18001697D
0x18001693f  test    [rsp+48h+arg_20], 0FFFFFFEAh
0x180016947  jnz     loc_180016B17
0x18001694d  cmp     r9d, 2
0x180016951  jz      loc_180016B17
0x180016957  movzx   edi, cs:Tcpip6_TdiModeDgram
0x18001695e  lea     rdx, aDeviceUdp6; "\\Device\\Udp6"
0x180016965  mov     dword ptr [rbx], 17h
0x18001696b  mov     dword ptr [r14], 2
0x180016972  mov     dword ptr [rsi], 11h
0x180016978  jmp     loc_180016894
0x18001697d  cmp     r11d, 3
0x180016981  jz      short loc_18001693F
0x180016983  inc     edx
0x180016985  jmp     short loc_180016910
0x180016987  inc     edx
0x180016989  cmp     edx, 2
0x18001698c  jnb     loc_180016B17
0x180016992  lea     rcx, [rdx+rdx*2]
0x180016996  mov     eax, ds:rva Tcpip6_RawMappingTriples[r8+rcx*4]
0x18001699e  cmp     [rbx], eax
0x1800169a0  jnz     short loc_180016987
0x1800169a2  cmp     r11d, ds:rva dword_18005B094[r8+rcx*4]
0x1800169aa  jnz     short loc_180016987
0x1800169ac  mov     eax, [rsi]
0x1800169ae  cmp     eax, ds:rva dword_18005B098[r8+rcx*4]
0x1800169b6  jz      short loc_1800169BE
0x1800169b8  cmp     r11d, 3
0x1800169bc  jnz     short loc_180016987
0x1800169be  test    [rsp+48h+arg_20], 0FFFFFFEAh
0x1800169c6  jnz     loc_180016B17
0x1800169cc  cmp     eax, 0FFh
0x1800169d1  ja      loc_180016B17
0x1800169d7  movzx   edi, cs:Tcpip6_TdiModeRaw
0x1800169de  test    dil, dil
0x1800169e1  jz      loc_180016AF2
0x1800169e7  xorps   xmm0, xmm0
0x1800169ea  lea     rdx, aDeviceRawip6; "\\Device\\RawIp6"
0x1800169f1  lea     rcx, [rsp+48h+Source]; DestinationString
0x1800169f6  movups  xmmword ptr [rsp+48h+Source.Length], xmm0
0x1800169fb  call    cs:__imp_RtlInitUnicodeString
0x180016a02  nop     dword ptr [rax+rax+00h]
0x180016a07  mov     rbp, [rsp+48h+DestinationString]
0x180016a0c  xor     edx, edx; SourceString
0x180016a0e  mov     rcx, rbp; DestinationString
0x180016a11  call    cs:__imp_RtlInitUnicodeString
0x180016a18  nop     dword ptr [rax+rax+00h]
0x180016a1d  movzx   eax, [rsp+48h+Source.Length]
0x180016a22  xor     edx, edx; Flags
0x180016a24  add     ax, 0Ah
0x180016a28  movzx   r8d, ax; Size
0x180016a2c  mov     [rbp+2], r8w
0x180016a31  mov     rcx, gs:60h
0x180016a3a  mov     rcx, [rcx+30h]; HeapHandle
0x180016a3e  call    cs:__imp_RtlAllocateHeap
0x180016a45  nop     dword ptr [rax+rax+00h]
0x180016a4a  mov     [rbp+8], rax
0x180016a4e  test    rax, rax
0x180016a51  jnz     short loc_180016A6B
0x180016a53  mov     eax, 2747h
0x180016a58  jmp     loc_1800168E8
0x180016a5d  xor     edx, edx
0x180016a5f  jmp     loc_180016910
0x180016a64  xor     edx, edx
0x180016a66  jmp     loc_180016989
0x180016a6b  lea     rdx, [rsp+48h+Source]; Source
0x180016a70  mov     rcx, rbp; Destination
0x180016a73  call    cs:__imp_RtlAppendUnicodeStringToString
0x180016a7a  nop     dword ptr [rax+rax+00h]
0x180016a7f  movzx   ecx, word ptr [rbp+0]
0x180016a83  lea     r8, [rsp+48h+Source]; String
0x180016a88  mov     rax, [rbp+8]
0x180016a8c  shr     rcx, 1
0x180016a8f  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180016a95  xor     eax, eax
0x180016a97  add     word ptr [rbp+0], 2
0x180016a9c  movzx   edx, word ptr [rbp+0]
0x180016aa0  mov     rcx, [rbp+8]
0x180016aa4  shr     rdx, 1
0x180016aa7  mov     [rcx+rdx*2], ax
0x180016aab  movzx   edx, word ptr [rbp+0]
0x180016aaf  mov     rax, [rbp+8]
0x180016ab3  mov     ecx, edx
0x180016ab5  shr     rcx, 1
0x180016ab8  lea     rcx, [rax+rcx*2]
0x180016abc  xor     eax, eax
0x180016abe  mov     [rsp+48h+Source.Length], ax
0x180016ac3  movzx   eax, word ptr [rbp+2]
0x180016ac7  sub     ax, dx
0x180016aca  mov     [rsp+48h+Source.Buffer], rcx
0x180016acf  mov     ecx, [rsi]; Value
0x180016ad1  mov     edx, 0Ah; Base
0x180016ad6  mov     [rsp+48h+Source.MaximumLength], ax
0x180016adb  call    cs:__imp_RtlIntegerToUnicodeString
0x180016ae2  nop     dword ptr [rax+rax+00h]
0x180016ae7  movzx   eax, [rsp+48h+Source.Length]
0x180016aec  add     [rbp+0], ax
0x180016af0  jmp     short loc_180016B05
0x180016af2  mov     rcx, [rsp+48h+DestinationString]; DestinationString
0x180016af7  xor     edx, edx; SourceString
0x180016af9  call    cs:__imp_RtlInitUnicodeString
0x180016b00  nop     dword ptr [rax+rax+00h]
0x180016b05  mov     dword ptr [rbx], 17h
0x180016b0b  mov     dword ptr [r14], 3
0x180016b12  jmp     loc_1800168AE
0x180016b17  mov     eax, 2726h
0x180016b1c  jmp     loc_1800168E8
```
