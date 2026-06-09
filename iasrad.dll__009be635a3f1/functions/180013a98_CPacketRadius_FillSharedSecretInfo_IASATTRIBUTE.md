# CPacketRadius::FillSharedSecretInfo(_IASATTRIBUTE *)

- ea: `0x180013a98`
- end: `0x180013b72`
- name: `?FillSharedSecretInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(CPacketRadius *__hidden this, struct _IASATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c68`

## callees

- `0x180002106`
- `0x1800094e4`
- `0x180013a98`
- `0x18001d31c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013acf`

## string_xrefs

- `0x180013b00`: `Unable to allocate memory for client secret during in-packet processing`

## pseudocode

```c
__int64 __fastcall CPacketRadius::FillSharedSecretInfo(CPacketRadius *this, struct _IASATTRIBUTE *a2)
{
  unsigned int v3; // edi
  const void *v4; // rsi
  void *v5; // rax
  SIZE_T cb; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  LODWORD(cb) = 0;
  v4 = (const void *)(*(__int64 (__fastcall **)(_QWORD, SIZE_T *))(**((_QWORD **)this + 16) + 72LL))(
                       *((_QWORD *)this + 16),
                       &cb);
  v5 = CoTaskMemAlloc((unsigned int)cb);
  *((_QWORD *)a2 + 4) = v5;
  if ( v5 )
  {
    *((_DWORD *)a2 + 2) = 4107;
    *((_DWORD *)a2 + 4) = 6;
    memcpy_0(v5, v4, (unsigned int)cb);
    *((_DWORD *)a2 + 6) = cb;
    *((_DWORD *)a2 + 1) = 16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate memory for client secret during in-packet processing");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids, "NPSRAD");
    }
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x180013a98  mov     [rsp+arg_0], rbx
0x180013a9d  mov     [rsp+arg_8], rsi
0x180013aa2  push    rdi
0x180013aa3  sub     rsp, 20h
0x180013aa7  mov     rbx, rdx
0x180013aaa  xor     edi, edi
0x180013aac  mov     dword ptr [rsp+28h+cb], edi
0x180013ab0  mov     rcx, [rcx+80h]
0x180013ab7  mov     rax, [rcx]
0x180013aba  lea     rdx, [rsp+28h+cb]
0x180013abf  mov     rax, [rax+48h]
0x180013ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac8  mov     rsi, rax
0x180013acb  mov     ecx, dword ptr [rsp+28h+cb]; cb
0x180013acf  call    cs:__imp_CoTaskMemAlloc
0x180013ad5  mov     [rbx+20h], rax
0x180013ad9  test    rax, rax
0x180013adc  jnz     short loc_180013B34
0x180013ade  lea     rcx, WPP_GLOBAL_Control
0x180013ae5  mov     rax, cs:WPP_GLOBAL_Control
0x180013aec  cmp     rax, rcx
0x180013aef  jz      short loc_180013B2D
0x180013af1  cmp     byte ptr [rax+19h], 2
0x180013af5  jb      short loc_180013B2D
0x180013af7  test    dword ptr [rax+1Ch], 100h
0x180013afe  jz      short loc_180013B2D
0x180013b00  lea     rcx, aUnableToAlloca_4; "Unable to allocate memory for client se"...
0x180013b07  call    WppDbgPrint
0x180013b0c  lea     edx, [rdi+1Fh]
0x180013b0f  lea     r9, aNpsrad; "NPSRAD"
0x180013b16  lea     r8, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids
0x180013b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b24  mov     rcx, [rcx+10h]
0x180013b28  call    WPP_SF_s
0x180013b2d  mov     edi, 8007000Eh
0x180013b32  jmp     short loc_180013B60
0x180013b34  mov     dword ptr [rbx+8], 100Bh
0x180013b3b  mov     dword ptr [rbx+10h], 6
0x180013b42  mov     r8d, dword ptr [rsp+28h+cb]; Size
0x180013b47  mov     rdx, rsi; Src
0x180013b4a  mov     rcx, rax; void *
0x180013b4d  call    memcpy_0
0x180013b52  mov     ecx, dword ptr [rsp+28h+cb]
0x180013b56  mov     [rbx+18h], ecx
0x180013b59  mov     dword ptr [rbx+4], 10h
0x180013b60  mov     eax, edi
0x180013b62  mov     rbx, [rsp+28h+arg_0]
0x180013b67  mov     rsi, [rsp+28h+arg_8]
0x180013b6c  add     rsp, 20h
0x180013b70  pop     rdi
0x180013b71  retn
0x18002e91b  push    rbp
0x18002e91d  sub     rsp, 20h
0x18002e921  mov     rbp, rdx
0x18002e924  add     rsp, 20h
0x18002e928  pop     rbp
0x18002e929  retn
```
