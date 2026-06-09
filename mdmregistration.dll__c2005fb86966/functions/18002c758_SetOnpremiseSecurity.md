# SetOnpremiseSecurity

- ea: `0x18002c758`
- end: `0x18002c801`
- name: `SetOnpremiseSecurity`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c808`

## callees

- `0x1800141b0`
- `0x18002b0ac`
- `0x18002c758`

## string_xrefs

- `0x18002c779`: `SetOnpremiseSecurity`
- `0x18002c79a`: `//wsse:Security//wsse:UsernameToken//wsse:Username`
- `0x18002c7bc`: `//wsse:Security//wsse:UsernameToken//wsse:Password`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetOnpremiseSecurity(
        struct IXMLDOMDocument2 *a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // ebx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v9; // [rsp+40h] [rbp+8h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = a1;
  v10 = 0;
  v8[0] = "SetOnpremiseSecurity";
  v8[1] = &v10;
  if ( a3 && (a2 || a4) )
  {
    v6 = HlpSetNodeString(&v9, L"//wsse:Security//wsse:UsernameToken//wsse:Username", a3);
    v10 = v6;
    if ( v6 >= 0 && !a2 )
    {
      v6 = HlpSetNodeString(&v9, L"//wsse:Security//wsse:UsernameToken//wsse:Password", a4);
      v10 = v6;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v8);
    return (unsigned int)v6;
  }
  else
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002c758  mov     r11, rsp
0x18002c75b  mov     [r11+10h], rbx
0x18002c75f  mov     [r11+20h], rsi
0x18002c763  mov     [r11+8], rcx
0x18002c767  push    rdi
0x18002c768  sub     rsp, 30h
0x18002c76c  mov     rsi, r9
0x18002c76f  mov     edi, edx
0x18002c771  mov     [rsp+38h+arg_10], 0
0x18002c779  lea     rax, aSetonpremisese; "SetOnpremiseSecurity"
0x18002c780  mov     [r11-18h], rax
0x18002c784  lea     rax, [r11+18h]
0x18002c788  mov     [r11-10h], rax
0x18002c78c  test    r8, r8
0x18002c78f  jz      short loc_18002C7E1
0x18002c791  test    edx, edx
0x18002c793  jnz     short loc_18002C79A
0x18002c795  test    r9, r9
0x18002c798  jz      short loc_18002C7E1
0x18002c79a  lea     rdx, aWsseSecurityWs; "//wsse:Security//wsse:UsernameToken//ws"...
0x18002c7a1  lea     rcx, [rsp+38h+arg_0]; struct IXMLDOMDocument2 **
0x18002c7a6  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c7ab  mov     ebx, eax
0x18002c7ad  mov     [rsp+38h+arg_10], eax
0x18002c7b1  test    eax, eax
0x18002c7b3  js      short loc_18002C7D3
0x18002c7b5  test    edi, edi
0x18002c7b7  jnz     short loc_18002C7D3
0x18002c7b9  mov     r8, rsi; unsigned __int16 *
0x18002c7bc  lea     rdx, aWsseSecurityWs_0; "//wsse:Security//wsse:UsernameToken//ws"...
0x18002c7c3  lea     rcx, [rsp+38h+arg_0]; struct IXMLDOMDocument2 **
0x18002c7c8  call    ?HlpSetNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG1@Z; HlpSetNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *)
0x18002c7cd  mov     ebx, eax
0x18002c7cf  mov     [rsp+38h+arg_10], eax
0x18002c7d3  lea     rcx, [rsp+38h+var_18]; this
0x18002c7d8  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002c7dd  mov     eax, ebx
0x18002c7df  jmp     short loc_18002C7F0
0x18002c7e1  lea     rcx, [rsp+38h+var_18]; this
0x18002c7e6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002c7eb  mov     eax, 80070057h
0x18002c7f0  mov     rbx, [rsp+38h+arg_8]
0x18002c7f5  mov     rsi, [rsp+38h+arg_18]
0x18002c7fa  add     rsp, 30h
0x18002c7fe  pop     rdi
0x18002c7ff  retn
```
