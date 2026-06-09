# container::MountManager::SetVolumeNameForRoot(void *,ushort,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180025840`
- end: `0x180025aa0`
- name: `?SetVolumeNameForRoot@MountManager@container@@YAHPEAXGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002562c`

## callees

- `0x180002ad0`
- `0x180003614`
- `0x180003620`
- `0x18000362c`
- `0x1800051b0`
- `0x18000cd50`
- `0x18001d534`
- `0x18001d894`
- `0x18001e6dc`
- `0x180023e64`
- `0x180025840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002589f`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a45`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025a33`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025a33`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall container::MountManager::SetVolumeNameForRoot(HANDLE hDevice, wint_t a2, const void **a3)
{
  wint_t v5; // di
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  void **v8; // rcx
  unsigned __int16 v9; // r15
  __int64 v10; // r12
  unsigned __int64 v11; // rdi
  signed __int64 v12; // rcx
  char *v13; // rax
  unsigned __int64 v14; // rbx
  _WORD *v15; // rbx
  void **v16; // rdx
  const void *v17; // rdx
  unsigned int v18; // ebx
  void *lpInBuffer[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v21; // [rsp+50h] [rbp-19h]
  DWORD BytesReturned; // [rsp+58h] [rbp-11h] BYREF
  const void **v23; // [rsp+60h] [rbp-9h]
  void *Src[2]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v25; // [rsp+78h] [rbp+Fh]
  unsigned __int64 v26; // [rsp+80h] [rbp+17h]

  v23 = a3;
  *(_OWORD *)lpInBuffer = 0;
  v21 = 0;
  BytesReturned = 0;
  *(_OWORD *)Src = 0;
  v25 = 0;
  v26 = 7;
  LOWORD(Src[0]) = 0;
  v5 = towupper(a2);
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    Src,
    12,
    v6,
    L"\\DosDevices\\");
  v7 = v25;
  v8 = Src;
  if ( v25 >= v26 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v25;
    if ( v26 > 7 )
      v8 = (void **)Src[0];
    *((_WORD *)v8 + v7) = v5;
    *((_WORD *)v8 + v7 + 1) = 0;
  }
  std::wstring::append(Src, L":");
  v9 = 2 * v25;
  v10 = 2LL * (_QWORD)a3[2];
  v11 = v10 + 2 * v25 + 8;
  v12 = (char *)lpInBuffer[1] - (char *)lpInBuffer[0];
  if ( v11 >= (char *)lpInBuffer[1] - (char *)lpInBuffer[0] )
  {
    if ( v11 <= (char *)lpInBuffer[1] - (char *)lpInBuffer[0] )
      goto LABEL_13;
    if ( v11 > v21 - (unsigned __int64)lpInBuffer[0] )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpInBuffer, v11);
      goto LABEL_13;
    }
    v14 = v11 - v12;
    memset_0(lpInBuffer[1], 0, v11 - v12);
    v13 = (char *)lpInBuffer[1] + v14;
  }
  else
  {
    v13 = (char *)lpInBuffer[0] + v11;
  }
  lpInBuffer[1] = v13;
LABEL_13:
  memset_0(lpInBuffer[0], 0, v11);
  v15 = lpInBuffer[0];
  *(_WORD *)lpInBuffer[0] = 8;
  v15[1] = v9;
  v15[2] = v9 + 8;
  v15[3] = v10;
  v16 = Src;
  if ( v26 > 7 )
    v16 = (void **)Src[0];
  memcpy_0((char *)lpInBuffer[0] + 8, v16, v9);
  if ( (unsigned __int64)a3[3] <= 7 )
    v17 = a3;
  else
    v17 = *a3;
  memcpy_0((char *)lpInBuffer[0] + (unsigned __int16)v15[2], v17, (unsigned __int16)v15[3]);
  v18 = DeviceIoControl(hDevice, 0x6DC000u, v15, v11, 0, 0, &BytesReturned, 0);
  if ( !v18 )
    v18 = GetLastError() == 87;
  std::wstring::~wstring(Src);
  std::vector<unsigned char>::~vector<unsigned char>(lpInBuffer);
  std::wstring::~wstring(a3);
  return v18;
}

```

## disassembly

```asm
0x180025840  mov     [rsp-8+arg_18], rbx
0x180025845  push    rbp
0x180025846  push    rsi
0x180025847  push    rdi
0x180025848  push    r12
0x18002584a  push    r13
0x18002584c  push    r14
0x18002584e  push    r15
0x180025850  lea     rbp, [rsp-27h]
0x180025855  sub     rsp, 90h
0x18002585c  mov     rax, cs:__security_cookie
0x180025863  xor     rax, rsp
0x180025866  mov     [rbp+57h+var_38], rax
0x18002586a  mov     rsi, r8
0x18002586d  mov     r13, rcx
0x180025870  mov     [rbp+57h+var_60], r8
0x180025874  xorps   xmm0, xmm0
0x180025877  movdqu  xmmword ptr [rbp+57h+lpInBuffer], xmm0
0x18002587c  xor     r14d, r14d
0x18002587f  mov     [rbp+57h+var_70], r14
0x180025883  mov     [rbp+57h+BytesReturned], r14d
0x180025887  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18002588b  mov     [rbp+57h+var_48], r14
0x18002588f  mov     [rbp+57h+var_40], 7
0x180025897  mov     word ptr [rbp+57h+Src], r14w
0x18002589c  movzx   ecx, dx; C
0x18002589f  call    cs:__imp_towupper
0x1800258a6  nop     dword ptr [rax+rax+00h]
0x1800258ab  movzx   edi, ax
0x1800258ae  lea     edx, [r14+0Ch]
0x1800258b2  cmp     [rbp+57h+var_40], rdx
0x1800258b6  jb      short loc_1800258E4
0x1800258b8  lea     rbx, [rbp+57h+Src]
0x1800258bc  cmp     [rbp+57h+var_40], 7
0x1800258c1  cmova   rbx, [rbp+57h+Src]
0x1800258c6  mov     [rbp+57h+var_48], rdx
0x1800258ca  lea     r8d, [r14+18h]; Size
0x1800258ce  lea     rdx, aDosdevices; "\\DosDevices\\"
0x1800258d5  mov     rcx, rbx; void *
0x1800258d8  call    memmove_0
0x1800258dd  mov     [rbx+18h], r14w
0x1800258e2  jmp     short loc_1800258F4
0x1800258e4  lea     r9, aDosdevices; "\\DosDevices\\"
0x1800258eb  lea     rcx, [rbp+57h+Src]
0x1800258ef  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800258f4  mov     rdx, [rbp+57h+var_48]
0x1800258f8  lea     rcx, [rbp+57h+Src]; Src
0x1800258fc  cmp     rdx, [rbp+57h+var_40]
0x180025900  jnb     short loc_180025920
0x180025902  lea     rax, [rdx+1]
0x180025906  mov     [rbp+57h+var_48], rax
0x18002590a  cmp     [rbp+57h+var_40], 7
0x18002590f  cmova   rcx, [rbp+57h+Src]
0x180025914  mov     [rcx+rdx*2], di
0x180025918  mov     [rcx+rdx*2+2], r14w
0x18002591e  jmp     short loc_180025929
0x180025920  movzx   r9d, di
0x180025924  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180025929  lea     rdx, asc_18003980C; ":"
0x180025930  lea     rcx, [rbp+57h+Src]; Src
0x180025934  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180025939  mov     rax, [rbp+57h+var_48]
0x18002593d  lea     r15, [rax+rax]
0x180025941  mov     rax, [rsi+10h]
0x180025945  lea     r12, [rax+rax]
0x180025949  lea     rdi, [r15+8]
0x18002594d  add     rdi, r12
0x180025950  mov     rdx, [rbp+57h+lpInBuffer]
0x180025954  mov     r14, [rbp+57h+lpInBuffer+8]
0x180025958  mov     rcx, r14
0x18002595b  sub     rcx, rdx
0x18002595e  cmp     rdi, rcx
0x180025961  jnb     short loc_180025969
0x180025963  lea     rax, [rdi+rdx]
0x180025967  jmp     short loc_18002599C
0x180025969  jbe     short loc_1800259A0
0x18002596b  mov     rax, [rbp+57h+var_70]
0x18002596f  sub     rax, rdx
0x180025972  cmp     rdi, rax
0x180025975  jbe     short loc_180025985
0x180025977  mov     rdx, rdi
0x18002597a  lea     rcx, [rbp+57h+lpInBuffer]
0x18002597e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180025983  jmp     short loc_1800259A0
0x180025985  mov     rbx, rdi
0x180025988  sub     rbx, rcx
0x18002598b  mov     r8, rbx; Size
0x18002598e  xor     edx, edx; Val
0x180025990  mov     rcx, r14; void *
0x180025993  call    memset_0
0x180025998  lea     rax, [rbx+r14]
0x18002599c  mov     [rbp+57h+lpInBuffer+8], rax
0x1800259a0  mov     r8, rdi; Size
0x1800259a3  xor     edx, edx; Val
0x1800259a5  mov     rcx, [rbp+57h+lpInBuffer]; void *
0x1800259a9  call    memset_0
0x1800259ae  mov     rbx, [rbp+57h+lpInBuffer]
0x1800259b2  mov     ecx, 8
0x1800259b7  mov     [rbx], cx
0x1800259ba  movzx   r8d, r15w; Size
0x1800259be  mov     [rbx+2], r8w
0x1800259c3  lea     eax, [rcx+r8]
0x1800259c7  mov     [rbx+4], ax
0x1800259cb  mov     [rbx+6], r12w
0x1800259d0  lea     rdx, [rbp+57h+Src]
0x1800259d4  cmp     [rbp+57h+var_40], 7
0x1800259d9  cmova   rdx, [rbp+57h+Src]; Src
0x1800259de  mov     rcx, [rbp+57h+lpInBuffer]
0x1800259e2  add     rcx, 8; void *
0x1800259e6  call    memcpy_0
0x1800259eb  movzx   r8d, word ptr [rbx+6]; Size
0x1800259f0  cmp     qword ptr [rsi+18h], 7
0x1800259f5  jbe     short loc_1800259FC
0x1800259f7  mov     rdx, [rsi]
0x1800259fa  jmp     short loc_1800259FF
0x1800259fc  mov     rdx, rsi; Src
0x1800259ff  movzx   ecx, word ptr [rbx+4]
0x180025a03  add     rcx, [rbp+57h+lpInBuffer]; void *
0x180025a07  call    memcpy_0
0x180025a0c  mov     r9d, edi; nInBufferSize
0x180025a0f  xor     edi, edi
0x180025a11  mov     [rsp+0C0h+lpOverlapped], rdi; lpOverlapped
0x180025a16  lea     rax, [rbp+57h+BytesReturned]
0x180025a1a  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x180025a1f  mov     [rsp+0C0h+nOutBufferSize], edi; nOutBufferSize
0x180025a23  mov     [rsp+0C0h+lpOutBuffer], rdi; lpOutBuffer
0x180025a28  mov     r8, rbx; lpInBuffer
0x180025a2b  mov     edx, 6DC000h; dwIoControlCode
0x180025a30  mov     rcx, r13; hDevice
0x180025a33  call    cs:__imp_DeviceIoControl
0x180025a3a  nop     dword ptr [rax+rax+00h]
0x180025a3f  mov     ebx, eax
0x180025a41  test    eax, eax
0x180025a43  jnz     short loc_180025A5A
0x180025a45  call    cs:__imp_GetLastError
0x180025a4c  nop     dword ptr [rax+rax+00h]
0x180025a51  lea     ecx, [rdi+1]
0x180025a54  cmp     eax, 57h ; 'W'
0x180025a57  cmovz   ebx, ecx
0x180025a5a  lea     rcx, [rbp+57h+Src]
0x180025a5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025a63  nop
0x180025a64  lea     rcx, [rbp+57h+lpInBuffer]
0x180025a68  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180025a6d  nop
0x180025a6e  mov     rcx, rsi
0x180025a71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025a76  mov     eax, ebx
0x180025a78  mov     rcx, [rbp+57h+var_38]
0x180025a7c  xor     rcx, rsp; StackCookie
0x180025a7f  call    __security_check_cookie
0x180025a84  mov     rbx, [rsp+0C0h+arg_18]
0x180025a8c  add     rsp, 90h
0x180025a93  pop     r15
0x180025a95  pop     r14
0x180025a97  pop     r13
0x180025a99  pop     r12
0x180025a9b  pop     rdi
0x180025a9c  pop     rsi
0x180025a9d  pop     rbp
0x180025a9e  retn
```
