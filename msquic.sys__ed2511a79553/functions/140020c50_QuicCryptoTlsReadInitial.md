# QuicCryptoTlsReadInitial

- ea: `0x140020c50`
- end: `0x140020d28`
- name: `QuicCryptoTlsReadInitial`
- size: `216`
- prototype: `__int64 __fastcall(__int64, _BYTE *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140009534`

## callees

- `0x140020c50`
- `0x140020d30`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003e3eb`
- `ntoskrnl!_snprintf_s` at `0x14003e3eb`

## string_xrefs

- `0x14003e41a`: `Invalid message in TlsReadInitial`
- `0x14003e3cd`: `No ALPN list extension present`
- `0x14003e3d6`: `No SNI extension present`

## pseudocode

```c
__int64 __fastcall QuicCryptoTlsReadInitial(__int64 a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  int v8; // ebx
  __int64 result; // rax
  const char *v10; // r9
  __int64 v11; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-B8h] BYREF

  do
  {
    if ( a3 < 4 )
      return 259;
    if ( *a2 != 1 )
    {
      if ( (byte_14005C48B & 4) != 0 )
      {
        v10 = "Invalid message in TlsReadInitial";
        goto LABEL_16;
      }
      return 3221225485LL;
    }
    v8 = (unsigned __int8)a2[3] + (((unsigned __int8)a2[2] + ((unsigned __int8)a2[1] << 8)) << 8);
    if ( a3 < v8 + 4 )
      return 259;
    result = QuicCryptoTlsReadClientHello(a1);
    if ( (int)result < 0 )
      return result;
    a3 += -4 - v8;
    a2 += (unsigned int)(v8 + 4);
  }
  while ( a3 );
  if ( !*(_QWORD *)(a4 + 48) )
  {
    if ( (byte_14005C48B & 4) != 0 )
    {
      v10 = "No ALPN list extension present";
LABEL_16:
      McTemplateU0ps_EtwWriteTransfer(a1, QuicConnError, a1, v10);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  if ( !*(_QWORD *)(a4 + 64) && (byte_14005C48B & 0x40) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "No SNI extension present");
    McTemplateU0ps_EtwWriteTransfer(v11, QuicConnLogWarning, a1, DstBuf);
  }
  return 0;
}

```

## disassembly

```asm
0x140020c50  mov     [rsp+arg_10], rbx
0x140020c55  push    rbp
0x140020c56  push    rsi
0x140020c57  push    rdi
0x140020c58  push    r14
0x140020c5a  push    r15
0x140020c5c  sub     rsp, 0B0h
0x140020c63  mov     rax, cs:__security_cookie
0x140020c6a  xor     rax, rsp
0x140020c6d  mov     [rsp+0D8h+var_38], rax
0x140020c75  mov     r14, r9
0x140020c78  mov     esi, r8d
0x140020c7b  mov     rdi, rdx
0x140020c7e  mov     rbp, rcx
0x140020c81  cmp     esi, 4
0x140020c84  jb      loc_14003E43A
0x140020c8a  cmp     byte ptr [rdi], 1
0x140020c8d  jnz     loc_14003E411
0x140020c93  movzx   eax, byte ptr [rdi+2]
0x140020c97  movzx   ebx, byte ptr [rdi+1]
0x140020c9b  shl     ebx, 8
0x140020c9e  add     ebx, eax
0x140020ca0  movzx   eax, byte ptr [rdi+3]
0x140020ca4  shl     ebx, 8
0x140020ca7  add     ebx, eax
0x140020ca9  lea     r15d, [rbx+4]
0x140020cad  cmp     esi, r15d
0x140020cb0  jb      loc_14003E43A
0x140020cb6  lea     rdx, [rdi+4]
0x140020cba  mov     r9, r14
0x140020cbd  mov     r8d, ebx
0x140020cc0  mov     rcx, rbp; int
0x140020cc3  call    QuicCryptoTlsReadClientHello
0x140020cc8  test    eax, eax
0x140020cca  js      short loc_140020D00
0x140020ccc  mov     eax, 0FFFFFFFCh
0x140020cd1  sub     eax, ebx
0x140020cd3  add     esi, eax
0x140020cd5  mov     eax, r15d
0x140020cd8  add     rdi, rax
0x140020cdb  test    esi, esi
0x140020cdd  jnz     short loc_140020C81
0x140020cdf  cmp     qword ptr [r14+30h], 0
0x140020ce4  jz      loc_14003E3C4
0x140020cea  cmp     qword ptr [r14+40h], 0
0x140020cef  jnz     short loc_140020CFE
0x140020cf1  test    cs:byte_14005C48B, 40h
0x140020cf8  jnz     loc_14003E3D6
0x140020cfe  xor     eax, eax
0x140020d00  mov     rcx, [rsp+0D8h+var_38]
0x140020d08  xor     rcx, rsp; StackCookie
0x140020d0b  call    __security_check_cookie
0x140020d10  mov     rbx, [rsp+0D8h+arg_10]
0x140020d18  add     rsp, 0B0h
0x140020d1f  pop     r15
0x140020d21  pop     r14
0x140020d23  pop     rdi
0x140020d24  pop     rsi
0x140020d25  pop     rbp
0x140020d26  retn
0x14003e3c4  test    cs:byte_14005C48B, 4
0x14003e3cb  jz      short loc_14003E430
0x14003e3cd  lea     r9, aNoAlpnListExte; "No ALPN list extension present"
0x14003e3d4  jmp     short loc_14003E421
0x14003e3d6  lea     r9, aNoSniExtension; "No SNI extension present"
0x14003e3dd  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003e3e1  mov     edx, 80h; SizeInBytes
0x14003e3e6  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14003e3eb  call    cs:__imp__snprintf_s
0x14003e3f2  nop     dword ptr [rax+rax+00h]
0x14003e3f7  lea     r9, [rsp+0D8h+DstBuf]
0x14003e3fc  mov     r8, rbp
0x14003e3ff  lea     rdx, QuicConnLogWarning
0x14003e406  call    McTemplateU0ps_EtwWriteTransfer
0x14003e40b  nop
0x14003e40c  jmp     loc_140020CFE
0x14003e411  test    cs:byte_14005C48B, 4
0x14003e418  jz      short loc_14003E430
0x14003e41a  lea     r9, aInvalidMessage; "Invalid message in TlsReadInitial"
0x14003e421  mov     r8, rbp
0x14003e424  lea     rdx, QuicConnError
0x14003e42b  call    McTemplateU0ps_EtwWriteTransfer
0x14003e430  mov     eax, 0C000000Dh
0x14003e435  jmp     loc_140020D00
0x14003e43a  mov     eax, 103h
0x14003e43f  jmp     loc_140020D00
```
