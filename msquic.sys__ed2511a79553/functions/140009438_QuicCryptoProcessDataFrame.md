# QuicCryptoProcessDataFrame

- ea: `0x140009438`
- end: `0x14000952b`
- name: `QuicCryptoProcessDataFrame`
- size: `243`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400093e4`

## callees

- `0x140009438`
- `0x14000fbc0`
- `0x14001c638`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003d730`
- `ntoskrnl!_snprintf_s` at `0x14003d7c6`
- `ntoskrnl!_snprintf_s` at `0x14003d730`
- `ntoskrnl!_snprintf_s` at `0x14003d7c6`

## string_xrefs

- `0x14003d76a`: `Tried to write beyond crypto flow control limit.`
- `0x14003d79d`: `Received %hu crypto bytes, offset=%llu Ready=%hhu`

## pseudocode

```c
__int64 __fastcall QuicCryptoProcessDataFrame(__int64 a1, int a2, __int64 a3, unsigned __int8 *a4)
{
  __int64 v5; // rdi
  __int64 v7; // rdx
  unsigned __int16 v8; // r8
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B0h] BYREF
  char DstBuf[128]; // [rsp+50h] [rbp-A8h] BYREF

  v5 = a1 - 2784;
  v16 = 0xFFFF;
  *a4 = 0;
  if ( !*(_QWORD *)(a3 + 8) )
  {
    v11 = 0;
LABEL_7:
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Received %hu crypto bytes, offset=%llu Ready=%hhu",
        *(unsigned __int16 *)(a3 + 8),
        *(_QWORD *)a3,
        *a4);
      McTemplateU0ps_EtwWriteTransfer(v14, QuicConnLogVerbose, v5, DstBuf);
    }
    return v11;
  }
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    v11 = 0;
    if ( (byte_14005C48B & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Ignoring received crypto after cleanup");
      McTemplateU0ps_EtwWriteTransfer(v13, QuicConnLogWarning, v5, DstBuf);
    }
    goto LABEL_7;
  }
  if ( (unsigned int)(a2 - 4) <= 1 )
    a2 = 3;
  if ( a2 < *(_DWORD *)(a1 + 24) )
    return 0;
  v7 = *(_QWORD *)a3 + *(unsigned int *)(a1 + 388);
  v8 = *(_WORD *)(a3 + 8);
  v15 = 0;
  v9 = QuicRecvBufferWrite(a1 + 392, v7, v8, *(_QWORD *)(a3 + 16), 0xFFFFu, &v16, (bool *)a4, &v15);
  v11 = v9;
  if ( v9 >= 0 )
    goto LABEL_7;
  if ( v9 == -1073741789 )
  {
    if ( (byte_14005C48B & 4) != 0 )
      McTemplateU0ps_EtwWriteTransfer(v10, QuicConnError, v5, "Tried to write beyond crypto flow control limit.");
    QuicConnCloseLocally(v5, 2, 13);
  }
  return v11;
}

```

## disassembly

```asm
0x140009438  mov     [rsp+arg_8], rbx
0x14000943d  push    rsi
0x14000943e  push    rdi
0x14000943f  push    r14
0x140009441  sub     rsp, 0E0h
0x140009448  mov     rax, cs:__security_cookie
0x14000944f  xor     rax, rsp
0x140009452  mov     [rsp+0F8h+var_28], rax
0x14000945a  mov     r14, r9
0x14000945d  lea     rdi, [rcx-0AE0h]
0x140009464  mov     r9d, 0FFFFh
0x14000946a  mov     rsi, r8
0x14000946d  mov     [rsp+0F8h+var_B0], r9
0x140009472  mov     byte ptr [r14], 0
0x140009476  cmp     qword ptr [r8+8], 0
0x14000947b  jz      loc_140009523
0x140009481  test    byte ptr [rcx], 1
0x140009484  jz      loc_14003D70C
0x14000948a  lea     eax, [rdx-4]
0x14000948d  mov     r8d, 3
0x140009493  cmp     eax, 1
0x140009496  cmovbe  edx, r8d
0x14000949a  cmp     edx, [rcx+18h]
0x14000949d  jl      loc_140009527
0x1400094a3  mov     edx, [rcx+184h]
0x1400094a9  lea     rax, [rsp+0F8h+var_B8]
0x1400094ae  add     rdx, [rsi]
0x1400094b1  add     rcx, 188h
0x1400094b8  movzx   r8d, word ptr [rsi+8]
0x1400094bd  and     [rsp+0F8h+var_B8], 0
0x1400094c3  mov     [rsp+0F8h+var_C0], rax
0x1400094c8  lea     rax, [rsp+0F8h+var_B0]
0x1400094cd  mov     [rsp+0F8h+var_C8], r14
0x1400094d2  mov     [rsp+0F8h+var_D0], rax
0x1400094d7  mov     [rsp+0F8h+var_D8], r9
0x1400094dc  mov     r9, [rsi+10h]
0x1400094e0  call    QuicRecvBufferWrite
0x1400094e5  mov     ebx, eax
0x1400094e7  test    eax, eax
0x1400094e9  js      loc_14003D756
0x1400094ef  test    cs:byte_14005C48C, 1
0x1400094f6  jnz     loc_14003D799
0x1400094fc  mov     eax, ebx
0x1400094fe  mov     rcx, [rsp+0F8h+var_28]
0x140009506  xor     rcx, rsp; StackCookie
0x140009509  call    __security_check_cookie
0x14000950e  mov     rbx, [rsp+0F8h+arg_8]
0x140009516  add     rsp, 0E0h
0x14000951d  pop     r14
0x14000951f  pop     rdi
0x140009520  pop     rsi
0x140009521  retn
0x140009523  xor     ebx, ebx
0x140009525  jmp     short loc_1400094EF
0x140009527  xor     ebx, ebx
0x140009529  jmp     short loc_1400094FC
0x14003d70c  xor     ebx, ebx
0x14003d70e  test    cs:byte_14005C48B, 40h
0x14003d715  jz      loc_1400094EF
0x14003d71b  lea     r9, aIgnoringReceiv; "Ignoring received crypto after cleanup"
0x14003d722  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003d726  mov     edx, 80h; SizeInBytes
0x14003d72b  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14003d730  call    cs:__imp__snprintf_s
0x14003d737  nop     dword ptr [rax+rax+00h]
0x14003d73c  lea     r9, [rsp+0F8h+DstBuf]
0x14003d741  mov     r8, rdi
0x14003d744  lea     rdx, QuicConnLogWarning
0x14003d74b  call    McTemplateU0ps_EtwWriteTransfer
0x14003d750  nop
0x14003d751  jmp     loc_1400094EF
0x14003d756  cmp     eax, 0C0000023h
0x14003d75b  jnz     loc_1400094FC
0x14003d761  test    cs:byte_14005C48B, 4
0x14003d768  jz      short loc_14003D780
0x14003d76a  lea     r9, aTriedToWriteBe_0; "Tried to write beyond crypto flow contr"...
0x14003d771  mov     r8, rdi
0x14003d774  lea     rdx, QuicConnError
0x14003d77b  call    McTemplateU0ps_EtwWriteTransfer
0x14003d780  xor     r9d, r9d
0x14003d783  mov     rcx, rdi
0x14003d786  lea     edx, [r9+2]
0x14003d78a  lea     r8d, [r9+0Dh]
0x14003d78e  call    QuicConnCloseLocally
0x14003d793  nop
0x14003d794  jmp     loc_1400094FC
0x14003d799  movzx   eax, byte ptr [r14]
0x14003d79d  lea     r9, aReceivedHuCryp; "Received %hu crypto bytes, offset=%llu "...
0x14003d7a4  movzx   ecx, word ptr [rsi+8]
0x14003d7a8  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003d7ac  mov     dword ptr [rsp+0F8h+var_C8], eax
0x14003d7b0  mov     edx, 80h; SizeInBytes
0x14003d7b5  mov     rax, [rsi]
0x14003d7b8  mov     [rsp+0F8h+var_D0], rax
0x14003d7bd  mov     dword ptr [rsp+0F8h+var_D8], ecx
0x14003d7c1  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14003d7c6  call    cs:__imp__snprintf_s
0x14003d7cd  nop     dword ptr [rax+rax+00h]
0x14003d7d2  lea     r9, [rsp+0F8h+DstBuf]
0x14003d7d7  mov     r8, rdi
0x14003d7da  lea     rdx, QuicConnLogVerbose
0x14003d7e1  call    McTemplateU0ps_EtwWriteTransfer
0x14003d7e6  nop
0x14003d7e7  jmp     loc_1400094FC
```
