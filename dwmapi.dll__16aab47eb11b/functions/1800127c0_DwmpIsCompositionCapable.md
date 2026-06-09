# DwmpIsCompositionCapable

- ea: `0x1800127c0`
- end: `0x18001285f`
- name: `DwmpIsCompositionCapable`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003370`
- `0x180004594`
- `0x180005b5c`
- `0x18000d0a0`
- `0x1800127c0`

## pseudocode

```c
__int64 __fastcall DwmpIsCompositionCapable(__int64 a1, _DWORD *a2, __int64 a3)
{
  unsigned int v4; // ebx
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApipIsCompositionCapable_Start,
      a3,
      1,
      (__int64)v6);
  if ( a2 )
  {
    v4 = 0;
    *a2 = 1;
  }
  else
  {
    v4 = -2147024809;
    DoStackCaptureDirect(-2147024809, 0x57u);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApipIsCompositionCapable_Stop,
      v4);
  return v4;
}

```

## disassembly

```asm
0x1800127c0  mov     [rsp+arg_0], rbx
0x1800127c5  push    rdi
0x1800127c6  sub     rsp, 50h
0x1800127ca  mov     rax, cs:__security_cookie
0x1800127d1  xor     rax, rsp
0x1800127d4  mov     [rsp+58h+var_18], rax
0x1800127d9  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x1800127e0  mov     rdi, rdx
0x1800127e3  jz      short loc_180012808
0x1800127e5  lea     rax, [rsp+58h+var_28]
0x1800127ea  mov     r9d, 1
0x1800127f0  lea     rdx, ApipIsCompositionCapable_Start
0x1800127f7  mov     [rsp+58h+var_38], rax
0x1800127fc  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180012803  call    McGenEventWrite_EtwEventWriteTransfer
0x180012808  test    rdi, rdi
0x18001280b  jnz     short loc_18001281E
0x18001280d  mov     ebx, 80070057h
0x180012812  lea     edx, [rdi+57h]; unsigned int
0x180012815  mov     ecx, ebx; int
0x180012817  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18001281c  jmp     short loc_180012826
0x18001281e  xor     ebx, ebx
0x180012820  mov     dword ptr [rdi], 1
0x180012826  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18001282d  jz      short loc_180012845
0x18001282f  mov     r8d, ebx
0x180012832  lea     rdx, ApipIsCompositionCapable_Stop
0x180012839  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180012840  call    McTemplateU0q_EtwEventWriteTransfer
0x180012845  mov     eax, ebx
0x180012847  mov     rcx, [rsp+58h+var_18]
0x18001284c  xor     rcx, rsp; StackCookie
0x18001284f  call    __security_check_cookie
0x180012854  mov     rbx, [rsp+58h+arg_0]
0x180012859  add     rsp, 50h
0x18001285d  pop     rdi
0x18001285e  retn
```
