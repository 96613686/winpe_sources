# MpSendPADSWithError

- ea: `0x140011560`
- end: `0x140011694`
- name: `MpSendPADSWithError`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1400108d4`

## callees

- `0x14000110c`
- `0x140005098`
- `0x140006b80`
- `0x140011560`
- `0x1400130a4`
- `0x1400138d0`
- `0x140015bb0`

## string_xrefs

- `0x140011605`: `Service not supported`

## pseudocode

```c
__int64 __fastcall MpSendPADSWithError(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rbx
  int v9; // edi
  int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  result = PacketInitializePADSToSend(a2, &v14, 0);
  v8 = v14;
  if ( !(_DWORD)result )
  {
    v9 = a3 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
LABEL_13:
          _InterlockedIncrement((volatile signed __int32 *)v8);
          LOBYTE(v7) = 1;
          ReferenceBinding(a1, v7);
          result = PrSend(a1, v8);
          goto LABEL_14;
        }
        v11 = 54;
        v12 = 514;
        v13 = "Can not accept any more connections from this machine";
      }
      else
      {
        v11 = 25;
        v13 = "AC-Cookie tag is invalid";
        v12 = 516;
      }
    }
    else
    {
      v11 = 22;
      v13 = "Service not supported";
      v12 = 513;
    }
    result = PacketInsertTag(v14, v12, v11, v13, 0);
    if ( !(_DWORD)result )
      goto LABEL_13;
  }
LABEL_14:
  if ( v8 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      result = (*(__int64 (__fastcall **)(__int64))(v8 + 8))(v8);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140011560  push    rbx
0x140011562  push    rsi
0x140011563  push    rdi
0x140011564  push    r14
0x140011566  sub     rsp, 38h
0x14001156a  mov     edi, r8d
0x14001156d  mov     [rsp+58h+arg_18], 0
0x140011576  mov     rbx, rdx
0x140011579  mov     rsi, rcx
0x14001157c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011583  lea     r14, WPP_GLOBAL_Control
0x14001158a  cmp     rcx, r14
0x14001158d  jz      short loc_1400115B1
0x14001158f  mov     eax, [rcx+2Ch]
0x140011592  test    al, 1
0x140011594  jz      short loc_1400115B1
0x140011596  cmp     byte ptr [rcx+29h], 3
0x14001159a  jb      short loc_1400115B1
0x14001159c  mov     rcx, [rcx+18h]
0x1400115a0  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400115a7  mov     edx, 80h
0x1400115ac  call    WPP_SF_
0x1400115b1  xor     r8d, r8d
0x1400115b4  lea     rdx, [rsp+58h+arg_18]
0x1400115b9  mov     rcx, rbx
0x1400115bc  call    PacketInitializePADSToSend
0x1400115c1  mov     rbx, [rsp+58h+arg_18]
0x1400115c6  test    eax, eax
0x1400115c8  jnz     short loc_14001163E
0x1400115ca  sub     edi, 1
0x1400115cd  jz      short loc_1400115FF
0x1400115cf  sub     edi, 1
0x1400115d2  jz      short loc_1400115EB
0x1400115d4  cmp     edi, 1
0x1400115d7  jnz     short loc_140011626
0x1400115d9  lea     r8d, [rax+36h]
0x1400115dd  mov     edx, 202h
0x1400115e2  lea     r9, aCanNotAcceptAn; "Can not accept any more connections fro"...
0x1400115e9  jmp     short loc_140011611
0x1400115eb  mov     r8d, 19h
0x1400115f1  lea     r9, aAcCookieTagIsI; "AC-Cookie tag is invalid"
0x1400115f8  mov     edx, 204h
0x1400115fd  jmp     short loc_140011611
0x1400115ff  mov     r8d, 16h
0x140011605  lea     r9, aServiceNotSupp; "Service not supported"
0x14001160c  mov     edx, 201h
0x140011611  mov     rcx, rbx
0x140011614  mov     [rsp+58h+var_38], 0
0x14001161d  call    PacketInsertTag
0x140011622  test    eax, eax
0x140011624  jnz     short loc_14001163E
0x140011626  lock inc dword ptr [rbx]
0x140011629  mov     dl, 1
0x14001162b  mov     rcx, rsi
0x14001162e  call    ReferenceBinding
0x140011633  mov     rdx, rbx
0x140011636  mov     rcx, rsi
0x140011639  call    PrSend
0x14001163e  test    rbx, rbx
0x140011641  jz      short loc_14001165B
0x140011643  or      eax, 0FFFFFFFFh
0x140011646  lock xadd [rbx], eax
0x14001164a  cmp     eax, 1
0x14001164d  jnz     short loc_14001165B
0x14001164f  mov     rax, [rbx+8]
0x140011653  mov     rcx, rbx
0x140011656  call    _guard_dispatch_icall
0x14001165b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011662  cmp     rcx, r14
0x140011665  jz      short loc_140011689
0x140011667  mov     eax, [rcx+2Ch]
0x14001166a  test    al, 1
0x14001166c  jz      short loc_140011689
0x14001166e  cmp     byte ptr [rcx+29h], 3
0x140011672  jb      short loc_140011689
0x140011674  mov     rcx, [rcx+18h]
0x140011678  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14001167f  mov     edx, 81h
0x140011684  call    WPP_SF_
0x140011689  add     rsp, 38h
0x14001168d  pop     r14
0x14001168f  pop     rdi
0x140011690  pop     rsi
0x140011691  pop     rbx
0x140011692  retn
```
