# MsQuicConfigurationLoadCredential

- ea: `0x140020010`
- end: `0x1400200cf`
- name: `MsQuicConfigurationLoadCredential`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140020010`
- `0x1400207e0`
- `0x14002974c`
- `0x140036138`
- `0x14003eca4`
- `0x140040c2c`

## pseudocode

```c
__int64 __fastcall MsQuicConfigurationLoadCredential(__int64 a1, unsigned int *a2)
{
  _DWORD *v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rdx
  int v6; // eax

  v3 = (_DWORD *)a1;
  v4 = -1073741811;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, (__int64)a2, 7, a1);
  if ( v3 )
  {
    if ( a2 )
    {
      a1 = 1;
      if ( *v3 == 1 )
      {
        CxPlatRefIncrement(v3 + 10);
        v6 = CxPlatTlsSecConfigCreate(a2, v5, (__int64)&QuicTlsCallbacks, (__int64)v3);
        a1 = a2[1];
        v4 = v6;
        if ( (a1 & 2) == 0 || v6 < 0 )
          QuicConfigurationRelease((__int64)v3);
      }
    }
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicApiExitStatus, v4);
  return v4;
}

```

## disassembly

```asm
0x140020010  mov     [rsp+arg_0], rbx
0x140020015  mov     [rsp+arg_8], rsi
0x14002001a  push    rdi
0x14002001b  sub     rsp, 30h
0x14002001f  test    cs:Microsoft_QuicEnableBits, 8
0x140020026  mov     rsi, rdx
0x140020029  mov     rbx, rcx
0x14002002c  mov     edi, 0C000000Dh
0x140020031  jz      short loc_140020041
0x140020033  mov     r9, rcx
0x140020036  mov     r8d, 7
0x14002003c  call    McTemplateU0qp_EtwWriteTransfer
0x140020041  test    rbx, rbx
0x140020044  jz      short loc_1400200A4
0x140020046  test    rsi, rsi
0x140020049  jz      short loc_1400200A4
0x14002004b  mov     ecx, 1
0x140020050  cmp     [rbx], ecx
0x140020052  jnz     short loc_1400200A4
0x140020054  mov     eax, [rsi+4]
0x140020057  xor     edx, edx
0x140020059  test    cl, al
0x14002005b  jnz     short loc_140020067
0x14002005d  test    byte ptr [rbx+0EBh], 30h
0x140020064  cmovz   edx, ecx
0x140020067  lea     rcx, [rbx+28h]
0x14002006b  call    CxPlatRefIncrement
0x140020070  lea     r8, MsQuicConfigurationLoadCredentialComplete
0x140020077  mov     r9, rbx
0x14002007a  mov     [rsp+38h+var_18], r8
0x14002007f  mov     rcx, rsi
0x140020082  lea     r8, QuicTlsCallbacks
0x140020089  call    CxPlatTlsSecConfigCreate
0x14002008e  mov     ecx, [rsi+4]
0x140020091  mov     edi, eax
0x140020093  test    cl, 2
0x140020096  jz      short loc_14002009C
0x140020098  test    eax, eax
0x14002009a  jns     short loc_1400200A4
0x14002009c  mov     rcx, rbx
0x14002009f  call    QuicConfigurationRelease
0x1400200a4  test    cs:Microsoft_QuicEnableBits, 8
0x1400200ab  jz      short loc_1400200BC
0x1400200ad  mov     r8d, edi
0x1400200b0  lea     rdx, QuicApiExitStatus
0x1400200b7  call    McTemplateU0q_EtwWriteTransfer
0x1400200bc  mov     rbx, [rsp+38h+arg_0]
0x1400200c1  mov     eax, edi
0x1400200c3  mov     rsi, [rsp+38h+arg_8]
0x1400200c8  add     rsp, 30h
0x1400200cc  pop     rdi
0x1400200cd  retn
```
