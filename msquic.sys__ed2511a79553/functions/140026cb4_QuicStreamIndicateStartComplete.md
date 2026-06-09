# QuicStreamIndicateStartComplete

- ea: `0x140026cb4`
- end: `0x140026d96`
- name: `QuicStreamIndicateStartComplete`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014630`
- `0x140020458`
- `0x140026d9c`

## callees

- `0x14000b27c`
- `0x140026cb4`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140026d4d`
- `ntoskrnl!_snprintf_s` at `0x140026d4d`

## string_xrefs

- `0x140026d3d`: `Indicating QUIC_STREAM_EVENT_START_COMPLETE [Status=0x%x ID=%llu Accepted=%hhu]`

## pseudocode

```c
char __fastcall QuicStreamIndicateStartComplete(__int64 a1, int a2)
{
  char result; // al
  __int64 v5; // r9
  bool v6; // cl
  char v7; // dl
  __int64 v8; // rcx
  __int64 v9; // [rsp+40h] [rbp-69h] BYREF
  int v10; // [rsp+48h] [rbp-61h]
  int v11; // [rsp+4Ch] [rbp-5Dh]
  __int64 v12; // [rsp+50h] [rbp-59h]
  __int64 v13; // [rsp+58h] [rbp-51h]
  int v14; // [rsp+60h] [rbp-49h]
  char DstBuf[128]; // [rsp+70h] [rbp-39h] BYREF

  result = *(_BYTE *)(a1 + 88);
  if ( (result & 8) == 0 )
  {
    v5 = *(_QWORD *)(a1 + 80);
    *(_BYTE *)(a1 + 88) = result | 8;
    v6 = 0;
    v9 = 0;
    v11 = 0;
    v13 = 0;
    v14 = 0;
    v10 = a2;
    v12 = v5;
    if ( a2 >= 0 )
      v6 = (*(_BYTE *)(a1 + 98) & 0x20) == 0;
    v7 = v6 | v13 & 0xFE;
    LOBYTE(v13) = v7;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Indicating QUIC_STREAM_EVENT_START_COMPLETE [Status=0x%x ID=%llu Accepted=%hhu]",
        a2,
        v5,
        v7 & 1);
      McTemplateU0ps_EtwWriteTransfer(v8, QuicStreamLogVerbose, a1, DstBuf);
    }
    return QuicStreamIndicateEvent(a1, &v9);
  }
  return result;
}

```

## disassembly

```asm
0x140026cb4  mov     [rsp-8+arg_10], rbx
0x140026cb9  push    rbp
0x140026cba  lea     rbp, [rsp-57h]
0x140026cbf  sub     rsp, 100h
0x140026cc6  mov     rax, cs:__security_cookie
0x140026ccd  xor     rax, rsp
0x140026cd0  mov     [rbp+57h+var_10], rax
0x140026cd4  mov     al, [rcx+58h]
0x140026cd7  mov     r8d, edx
0x140026cda  mov     rbx, rcx
0x140026cdd  test    al, 8
0x140026cdf  jnz     loc_140026D78
0x140026ce5  mov     r9, [rbx+50h]
0x140026ce9  or      al, 8
0x140026ceb  mov     [rcx+58h], al
0x140026cee  xor     ecx, ecx
0x140026cf0  mov     [rbp+57h+var_C0], rcx
0x140026cf4  mov     [rbp+57h+var_B4], ecx
0x140026cf7  mov     [rbp+57h+var_A8], rcx
0x140026cfb  mov     [rbp+57h+var_A0], ecx
0x140026cfe  mov     [rbp+57h+var_B8], edx
0x140026d01  mov     [rbp+57h+var_B0], r9
0x140026d05  test    edx, edx
0x140026d07  js      short loc_140026D11
0x140026d09  test    byte ptr [rbx+62h], 20h
0x140026d0d  jnz     short loc_140026D11
0x140026d0f  mov     cl, 1
0x140026d11  mov     dl, byte ptr [rbp+57h+var_A8]
0x140026d14  and     dl, 0FEh
0x140026d17  or      dl, cl
0x140026d19  test    cs:byte_14005C48D, 1
0x140026d20  mov     byte ptr [rbp+57h+var_A8], dl
0x140026d23  jz      short loc_140026D6C
0x140026d25  movzx   eax, dl
0x140026d28  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x140026d2c  and     eax, 1
0x140026d2f  mov     edx, 80h; SizeInBytes
0x140026d34  mov     [rsp+100h+var_D0], eax
0x140026d38  mov     [rsp+100h+var_D8], r9
0x140026d3d  lea     r9, aIndicatingQuic_19; "Indicating QUIC_STREAM_EVENT_START_COMP"...
0x140026d44  mov     [rsp+100h+var_E0], r8d
0x140026d49  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140026d4d  call    cs:__imp__snprintf_s
0x140026d54  nop     dword ptr [rax+rax+00h]
0x140026d59  lea     r9, [rbp+57h+DstBuf]
0x140026d5d  mov     r8, rbx
0x140026d60  lea     rdx, QuicStreamLogVerbose
0x140026d67  call    McTemplateU0ps_EtwWriteTransfer
0x140026d6c  lea     rdx, [rbp+57h+var_C0]
0x140026d70  mov     rcx, rbx
0x140026d73  call    QuicStreamIndicateEvent
0x140026d78  mov     rcx, [rbp+57h+var_10]
0x140026d7c  xor     rcx, rsp; StackCookie
0x140026d7f  call    __security_check_cookie
0x140026d84  mov     rbx, [rsp+100h+arg_10]
0x140026d8c  add     rsp, 100h
0x140026d93  pop     rbp
0x140026d94  retn
```
