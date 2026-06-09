# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x180005d58`
- end: `0x180005ec4`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005300`
- `0x180005ba0`
- `0x180009854`
- `0x18000d890`
- `0x18000da60`

## callees

- `0x180005d58`
- `0x18000ab30`
- `0x180029fb4`
- `0x18002b010`

## pseudocode

```c
void __fastcall CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(__int64 a1, __int64 a2)
{
  void (__fastcall *v3)(__int64, GUID *); // rax
  const GUID *v4; // r8
  GUID v5; // [rsp+20h] [rbp-38h] BYREF
  GUID Buf2; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 )
  {
    v3 = *(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)a2 + 264LL);
    Buf2 = GUID_NULL;
    v5 = GUID_NULL;
    v3(a2, &Buf2);
    if ( !memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) )
    {
      (*(void (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)a2 + 80LL))(a2, &MF_MT_SUBTYPE, &v5);
      if ( !memcmp_0(&MEDIASUBTYPE_ARGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_ARGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB24, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB24;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB555, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB555;
      }
      else
      {
        if ( memcmp_0(&MEDIASUBTYPE_RGB565, &v5, 0x10u) )
          return;
        v4 = &MFVideoFormat_RGB565;
      }
      (*(void (__fastcall **)(__int64, const GUID *, const GUID *))(*(_QWORD *)a2 + 192LL))(a2, &MF_MT_SUBTYPE, v4);
    }
  }
}

```

## disassembly

```asm
0x180005d58  test    rdx, rdx
0x180005d5b  jz      locret_180005EA8
0x180005d61  mov     [rsp+arg_0], rbx
0x180005d66  mov     [rsp+arg_10], rsi
0x180005d6b  push    rdi
0x180005d6c  sub     rsp, 50h
0x180005d70  mov     rax, cs:__security_cookie
0x180005d77  xor     rax, rsp
0x180005d7a  mov     [rsp+58h+var_18], rax
0x180005d7f  mov     rax, [rdx]
0x180005d82  mov     rbx, rdx
0x180005d85  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180005d8c  lea     rdx, [rsp+58h+Buf2]
0x180005d91  mov     rcx, rbx
0x180005d94  mov     rax, [rax+108h]
0x180005d9b  movdqu  [rsp+58h+Buf2], xmm0
0x180005da1  movdqu  [rsp+58h+var_38], xmm0
0x180005da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dac  mov     esi, 10h
0x180005db1  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180005db6  mov     r8d, esi; Size
0x180005db9  lea     rcx, MEDIATYPE_Video; Buf1
0x180005dc0  call    memcmp_0
0x180005dc5  test    eax, eax
0x180005dc7  jnz     loc_180005E8C
0x180005dcd  mov     rax, [rbx]
0x180005dd0  lea     rdi, MF_MT_SUBTYPE
0x180005dd7  lea     r8, [rsp+58h+var_38]
0x180005ddc  mov     rdx, rdi
0x180005ddf  mov     rcx, rbx
0x180005de2  mov     rax, [rax+50h]
0x180005de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005deb  mov     r8d, esi; Size
0x180005dee  lea     rdx, [rsp+58h+var_38]; Buf2
0x180005df3  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x180005dfa  call    memcmp_0
0x180005dff  test    eax, eax
0x180005e01  jz      short loc_180005E70
0x180005e03  mov     r8d, esi; Size
0x180005e06  lea     rdx, [rsp+58h+var_38]; Buf2
0x180005e0b  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x180005e12  call    memcmp_0
0x180005e17  test    eax, eax
0x180005e19  jz      loc_180005EA9
0x180005e1f  mov     r8d, esi; Size
0x180005e22  lea     rdx, [rsp+58h+var_38]; Buf2
0x180005e27  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x180005e2e  call    memcmp_0
0x180005e33  test    eax, eax
0x180005e35  jz      short loc_180005EB2
0x180005e37  mov     r8d, esi; Size
0x180005e3a  lea     rdx, [rsp+58h+var_38]; Buf2
0x180005e3f  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x180005e46  call    memcmp_0
0x180005e4b  test    eax, eax
0x180005e4d  jz      short loc_180005EBB
0x180005e4f  mov     r8d, esi; Size
0x180005e52  lea     rdx, [rsp+58h+var_38]; Buf2
0x180005e57  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x180005e5e  call    memcmp_0
0x180005e63  test    eax, eax
0x180005e65  jnz     short loc_180005E8C
0x180005e67  lea     r8, MFVideoFormat_RGB565
0x180005e6e  jmp     short loc_180005E77
0x180005e70  lea     r8, MFVideoFormat_ARGB32
0x180005e77  mov     rax, [rbx]
0x180005e7a  mov     rdx, rdi
0x180005e7d  mov     rcx, rbx
0x180005e80  mov     rax, [rax+0C0h]
0x180005e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8c  mov     rcx, [rsp+58h+var_18]
0x180005e91  xor     rcx, rsp; StackCookie
0x180005e94  call    __security_check_cookie
0x180005e99  mov     rbx, [rsp+58h+arg_0]
0x180005e9e  mov     rsi, [rsp+58h+arg_10]
0x180005ea3  add     rsp, 50h
0x180005ea7  pop     rdi
0x180005ea8  retn
0x180005ea9  lea     r8, MFVideoFormat_RGB24
0x180005eb0  jmp     short loc_180005E77
0x180005eb2  lea     r8, MFVideoFormat_RGB32
0x180005eb9  jmp     short loc_180005E77
0x180005ebb  lea     r8, MFVideoFormat_RGB555
0x180005ec2  jmp     short loc_180005E77
```
