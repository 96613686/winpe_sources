# SIPolicyInitializeWellKnownSidBuffer

- ea: `0x180076a58`
- end: `0x180076d3f`
- name: `SIPolicyInitializeWellKnownSidBuffer`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800e4cb8`

## callees

- `0x18002bef0`
- `0x180076a58`

## import_xrefs

- `ntoskrnl!RtlInitializeSidEx` at `0x180076aae`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076ad7`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076afd`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b23`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b53`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b80`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076bad`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076bda`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c07`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c34`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c61`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076cc1`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076d1a`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076aae`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076ad7`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076afd`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b23`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b53`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076b80`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076bad`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076bda`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c07`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c34`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076c61`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076cc1`
- `ntoskrnl!RtlInitializeSidEx` at `0x180076d1a`

## pseudocode

```c
__int64 SIPolicyInitializeWellKnownSidBuffer()
{
  __int64 result; // rax
  __int64 v1; // [rsp+20h] [rbp-29h]
  __int64 v2; // [rsp+20h] [rbp-29h]
  __int64 v3; // [rsp+20h] [rbp-29h]
  __int64 v4; // [rsp+20h] [rbp-29h]
  __int64 v5; // [rsp+20h] [rbp-29h]
  __int64 v6; // [rsp+20h] [rbp-29h]
  __int64 v7; // [rsp+20h] [rbp-29h]
  __int64 v8; // [rsp+20h] [rbp-29h]
  __int64 v9; // [rsp+20h] [rbp-29h]
  __int64 v10; // [rsp+20h] [rbp-29h]
  __int64 v11; // [rsp+20h] [rbp-29h]
  __int64 v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+60h] [rbp+17h] BYREF
  __int16 v14; // [rsp+64h] [rbp+1Bh]
  int v15; // [rsp+68h] [rbp+1Fh] BYREF
  __int16 v16; // [rsp+6Ch] [rbp+23h]
  int v17; // [rsp+70h] [rbp+27h] BYREF
  __int16 v18; // [rsp+74h] [rbp+2Bh]

  v18 = 768;
  v17 = 0;
  v13 = 0;
  v14 = 1280;
  v15 = 0;
  v16 = 3840;
  result = RtlInitializeSidEx(g_SIPolicyWellKnownSids, &v17, 2, 3, 0);
  if ( (int)result >= 0 )
  {
    result = RtlInitializeSidEx(&dword_180049124, &v13, 1, 18, v1);
    if ( (int)result >= 0 )
    {
      result = RtlInitializeSidEx(qword_180049168, &v13, 1, 19, v2);
      if ( (int)result >= 0 )
      {
        result = RtlInitializeSidEx(&dword_1800491AC, &v13, 1, 20, v3);
        if ( (int)result >= 0 )
        {
          LODWORD(v4) = 544;
          result = RtlInitializeSidEx(qword_1800491F0, &v13, 2, 32, v4);
          if ( (int)result >= 0 )
          {
            LODWORD(v5) = 594;
            result = RtlInitializeSidEx(&dword_180049234, &v13, 2, 32, v5);
            if ( (int)result >= 0 )
            {
              LODWORD(v6) = 550;
              result = RtlInitializeSidEx(qword_180049278, &v13, 2, 32, v6);
              if ( (int)result >= 0 )
              {
                LODWORD(v7) = 551;
                result = RtlInitializeSidEx(&dword_1800492BC, &v13, 2, 32, v7);
                if ( (int)result >= 0 )
                {
                  LODWORD(v8) = 577;
                  result = RtlInitializeSidEx(qword_180049300, &v13, 2, 32, v8);
                  if ( (int)result >= 0 )
                  {
                    LODWORD(v9) = 559;
                    result = RtlInitializeSidEx(&dword_180049344, &v13, 2, 32, v9);
                    if ( (int)result >= 0 )
                    {
                      LODWORD(v10) = 568;
                      result = RtlInitializeSidEx(qword_180049388, &v13, 2, 32, v10);
                      if ( (int)result >= 0 )
                      {
                        LODWORD(v11) = 1430448594;
                        result = RtlInitializeSidEx(&dword_1800493CC, &v15, 8, 2, v11);
                        if ( (int)result >= 0 )
                        {
                          LODWORD(v12) = 95739096;
                          return RtlInitializeSidEx(qword_180049410, &v15, 8, 2, v12);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180076a58  push    rbp
0x180076a5a  push    rbx
0x180076a5b  push    rsi
0x180076a5c  push    rdi
0x180076a5d  lea     rbp, [rsp-3Fh]
0x180076a62  sub     rsp, 88h
0x180076a69  mov     rax, cs:__security_cookie
0x180076a70  xor     rax, rsp
0x180076a73  mov     [rbp+57h+var_28], rax
0x180076a77  xor     ebx, ebx
0x180076a79  mov     [rbp+57h+var_2C], 300h
0x180076a7f  lea     rdx, [rbp+57h+var_30]
0x180076a83  mov     [rbp+57h+var_30], ebx
0x180076a86  lea     rcx, g_SIPolicyWellKnownSids
0x180076a8d  mov     [rbp+57h+var_40], ebx
0x180076a90  mov     [rbp+57h+var_3C], 500h
0x180076a96  lea     edi, [rbx+2]
0x180076a99  mov     [rbp+57h+var_38], ebx
0x180076a9c  mov     r8d, edi
0x180076a9f  mov     [rbp+57h+var_34], 0F00h
0x180076aa5  lea     r9d, [rbx+3]
0x180076aa9  mov     [rsp+0A0h+var_80], rbx
0x180076aae  call    cs:__imp_RtlInitializeSidEx
0x180076ab5  nop     dword ptr [rax+rax+00h]
0x180076aba  test    eax, eax
0x180076abc  js      loc_180076D26
0x180076ac2  lea     esi, [rbx+1]
0x180076ac5  mov     r8d, esi
0x180076ac8  lea     r9d, [rbx+12h]
0x180076acc  lea     rdx, [rbp+57h+var_40]
0x180076ad0  lea     rcx, dword_180049124
0x180076ad7  call    cs:__imp_RtlInitializeSidEx
0x180076ade  nop     dword ptr [rax+rax+00h]
0x180076ae3  test    eax, eax
0x180076ae5  js      loc_180076D26
0x180076aeb  lea     r9d, [rbx+13h]
0x180076aef  mov     r8d, esi
0x180076af2  lea     rdx, [rbp+57h+var_40]
0x180076af6  lea     rcx, qword_180049168
0x180076afd  call    cs:__imp_RtlInitializeSidEx
0x180076b04  nop     dword ptr [rax+rax+00h]
0x180076b09  test    eax, eax
0x180076b0b  js      loc_180076D26
0x180076b11  lea     r9d, [rbx+14h]
0x180076b15  mov     r8d, esi
0x180076b18  lea     rdx, [rbp+57h+var_40]
0x180076b1c  lea     rcx, dword_1800491AC
0x180076b23  call    cs:__imp_RtlInitializeSidEx
0x180076b2a  nop     dword ptr [rax+rax+00h]
0x180076b2f  test    eax, eax
0x180076b31  js      loc_180076D26
0x180076b37  lea     esi, [rbx+20h]
0x180076b3a  mov     dword ptr [rsp+0A0h+var_80], 220h
0x180076b42  mov     r9d, esi
0x180076b45  lea     rdx, [rbp+57h+var_40]
0x180076b49  mov     r8d, edi
0x180076b4c  lea     rcx, qword_1800491F0
0x180076b53  call    cs:__imp_RtlInitializeSidEx
0x180076b5a  nop     dword ptr [rax+rax+00h]
0x180076b5f  test    eax, eax
0x180076b61  js      loc_180076D26
0x180076b67  mov     r9d, esi
0x180076b6a  mov     dword ptr [rsp+0A0h+var_80], 252h
0x180076b72  mov     r8d, edi
0x180076b75  lea     rdx, [rbp+57h+var_40]
0x180076b79  lea     rcx, dword_180049234
0x180076b80  call    cs:__imp_RtlInitializeSidEx
0x180076b87  nop     dword ptr [rax+rax+00h]
0x180076b8c  test    eax, eax
0x180076b8e  js      loc_180076D26
0x180076b94  mov     r9d, esi
0x180076b97  mov     dword ptr [rsp+0A0h+var_80], 226h
0x180076b9f  mov     r8d, edi
0x180076ba2  lea     rdx, [rbp+57h+var_40]
0x180076ba6  lea     rcx, qword_180049278
0x180076bad  call    cs:__imp_RtlInitializeSidEx
0x180076bb4  nop     dword ptr [rax+rax+00h]
0x180076bb9  test    eax, eax
0x180076bbb  js      loc_180076D26
0x180076bc1  mov     r9d, esi
0x180076bc4  mov     dword ptr [rsp+0A0h+var_80], 227h
0x180076bcc  mov     r8d, edi
0x180076bcf  lea     rdx, [rbp+57h+var_40]
0x180076bd3  lea     rcx, dword_1800492BC
0x180076bda  call    cs:__imp_RtlInitializeSidEx
0x180076be1  nop     dword ptr [rax+rax+00h]
0x180076be6  test    eax, eax
0x180076be8  js      loc_180076D26
0x180076bee  mov     r9d, esi
0x180076bf1  mov     dword ptr [rsp+0A0h+var_80], 241h
0x180076bf9  mov     r8d, edi
0x180076bfc  lea     rdx, [rbp+57h+var_40]
0x180076c00  lea     rcx, qword_180049300
0x180076c07  call    cs:__imp_RtlInitializeSidEx
0x180076c0e  nop     dword ptr [rax+rax+00h]
0x180076c13  test    eax, eax
0x180076c15  js      loc_180076D26
0x180076c1b  mov     r9d, esi
0x180076c1e  mov     dword ptr [rsp+0A0h+var_80], 22Fh
0x180076c26  mov     r8d, edi
0x180076c29  lea     rdx, [rbp+57h+var_40]
0x180076c2d  lea     rcx, dword_180049344
0x180076c34  call    cs:__imp_RtlInitializeSidEx
0x180076c3b  nop     dword ptr [rax+rax+00h]
0x180076c40  test    eax, eax
0x180076c42  js      loc_180076D26
0x180076c48  mov     r9d, esi
0x180076c4b  mov     dword ptr [rsp+0A0h+var_80], 238h
0x180076c53  mov     r8d, edi
0x180076c56  lea     rdx, [rbp+57h+var_40]
0x180076c5a  lea     rcx, qword_180049388
0x180076c61  call    cs:__imp_RtlInitializeSidEx
0x180076c68  nop     dword ptr [rax+rax+00h]
0x180076c6d  test    eax, eax
0x180076c6f  js      loc_180076D26
0x180076c75  mov     [rsp+0A0h+var_50], 4C2B8C5Ah
0x180076c7d  lea     esi, [rbx+8]
0x180076c80  mov     [rsp+0A0h+var_58], 0F28A92BCh
0x180076c88  lea     rdx, [rbp+57h+var_38]
0x180076c8c  mov     [rsp+0A0h+var_60], 4767CC4Fh
0x180076c94  lea     rcx, dword_1800493CC
0x180076c9b  mov     [rsp+0A0h+var_68], 1A2FA379h
0x180076ca3  mov     r9d, edi
0x180076ca6  mov     [rsp+0A0h+var_70], 3A0B3827h
0x180076cae  mov     r8d, esi
0x180076cb1  mov     [rsp+0A0h+var_78], 9D4F738Eh
0x180076cb9  mov     dword ptr [rsp+0A0h+var_80], 5542E9D2h
0x180076cc1  call    cs:__imp_RtlInitializeSidEx
0x180076cc8  nop     dword ptr [rax+rax+00h]
0x180076ccd  test    eax, eax
0x180076ccf  js      short loc_180076D26
0x180076cd1  mov     [rsp+0A0h+var_50], 0A3B6F52Bh
0x180076cd9  lea     rdx, [rbp+57h+var_38]
0x180076cdd  mov     [rsp+0A0h+var_58], 1A7CAEBBh
0x180076ce5  lea     rcx, qword_180049410
0x180076cec  mov     [rsp+0A0h+var_60], 64782BBFh
0x180076cf4  mov     r9d, edi
0x180076cf7  mov     [rsp+0A0h+var_68], 0E5B1155Bh
0x180076cff  mov     r8d, esi
0x180076d02  mov     [rsp+0A0h+var_70], 79318273h
0x180076d0a  mov     [rsp+0A0h+var_78], 1D02DE5Ch
0x180076d12  mov     dword ptr [rsp+0A0h+var_80], 5B4DCD8h
0x180076d1a  call    cs:__imp_RtlInitializeSidEx
0x180076d21  nop     dword ptr [rax+rax+00h]
0x180076d26  mov     rcx, [rbp+57h+var_28]
0x180076d2a  xor     rcx, rsp; StackCookie
0x180076d2d  call    __security_check_cookie
0x180076d32  add     rsp, 88h
0x180076d39  pop     rdi
0x180076d3a  pop     rsi
0x180076d3b  pop     rbx
0x180076d3c  pop     rbp
0x180076d3d  retn
```
