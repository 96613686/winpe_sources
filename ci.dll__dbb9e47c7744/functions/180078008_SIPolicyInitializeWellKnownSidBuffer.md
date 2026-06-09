# SIPolicyInitializeWellKnownSidBuffer

- ea: `0x180078008`
- end: `0x1800782ef`
- name: `SIPolicyInitializeWellKnownSidBuffer`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800e4ca8`

## callees

- `0x18002bf20`
- `0x180078008`

## import_xrefs

- `ntoskrnl!RtlInitializeSidEx` at `0x18007805e`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078087`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800780ad`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800780d3`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078103`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078130`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007815d`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007818a`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800781b7`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800781e4`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078211`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078271`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800782ca`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007805e`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078087`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800780ad`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800780d3`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078103`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078130`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007815d`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007818a`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800781b7`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800781e4`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078211`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078271`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800782ca`

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
    result = RtlInitializeSidEx(&dword_18004A104, &v13, 1, 18, v1);
    if ( (int)result >= 0 )
    {
      result = RtlInitializeSidEx(qword_18004A148, &v13, 1, 19, v2);
      if ( (int)result >= 0 )
      {
        result = RtlInitializeSidEx(&dword_18004A18C, &v13, 1, 20, v3);
        if ( (int)result >= 0 )
        {
          LODWORD(v4) = 544;
          result = RtlInitializeSidEx(qword_18004A1D0, &v13, 2, 32, v4);
          if ( (int)result >= 0 )
          {
            LODWORD(v5) = 594;
            result = RtlInitializeSidEx(&dword_18004A214, &v13, 2, 32, v5);
            if ( (int)result >= 0 )
            {
              LODWORD(v6) = 550;
              result = RtlInitializeSidEx(qword_18004A258, &v13, 2, 32, v6);
              if ( (int)result >= 0 )
              {
                LODWORD(v7) = 551;
                result = RtlInitializeSidEx(&dword_18004A29C, &v13, 2, 32, v7);
                if ( (int)result >= 0 )
                {
                  LODWORD(v8) = 577;
                  result = RtlInitializeSidEx(qword_18004A2E0, &v13, 2, 32, v8);
                  if ( (int)result >= 0 )
                  {
                    LODWORD(v9) = 559;
                    result = RtlInitializeSidEx(&dword_18004A324, &v13, 2, 32, v9);
                    if ( (int)result >= 0 )
                    {
                      LODWORD(v10) = 568;
                      result = RtlInitializeSidEx(qword_18004A368, &v13, 2, 32, v10);
                      if ( (int)result >= 0 )
                      {
                        LODWORD(v11) = 1430448594;
                        result = RtlInitializeSidEx(&dword_18004A3AC, &v15, 8, 2, v11);
                        if ( (int)result >= 0 )
                        {
                          LODWORD(v12) = 95739096;
                          return RtlInitializeSidEx(qword_18004A3F0, &v15, 8, 2, v12);
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
0x180078008  push    rbp
0x18007800a  push    rbx
0x18007800b  push    rsi
0x18007800c  push    rdi
0x18007800d  lea     rbp, [rsp-3Fh]
0x180078012  sub     rsp, 88h
0x180078019  mov     rax, cs:__security_cookie
0x180078020  xor     rax, rsp
0x180078023  mov     [rbp+57h+var_28], rax
0x180078027  xor     ebx, ebx
0x180078029  mov     [rbp+57h+var_2C], 300h
0x18007802f  lea     rdx, [rbp+57h+var_30]
0x180078033  mov     [rbp+57h+var_30], ebx
0x180078036  lea     rcx, g_SIPolicyWellKnownSids
0x18007803d  mov     [rbp+57h+var_40], ebx
0x180078040  mov     [rbp+57h+var_3C], 500h
0x180078046  lea     edi, [rbx+2]
0x180078049  mov     [rbp+57h+var_38], ebx
0x18007804c  mov     r8d, edi
0x18007804f  mov     [rbp+57h+var_34], 0F00h
0x180078055  lea     r9d, [rbx+3]
0x180078059  mov     [rsp+0A0h+var_80], rbx
0x18007805e  call    cs:__imp_RtlInitializeSidEx
0x180078065  nop     dword ptr [rax+rax+00h]
0x18007806a  test    eax, eax
0x18007806c  js      loc_1800782D6
0x180078072  lea     esi, [rbx+1]
0x180078075  mov     r8d, esi
0x180078078  lea     r9d, [rbx+12h]
0x18007807c  lea     rdx, [rbp+57h+var_40]
0x180078080  lea     rcx, dword_18004A104
0x180078087  call    cs:__imp_RtlInitializeSidEx
0x18007808e  nop     dword ptr [rax+rax+00h]
0x180078093  test    eax, eax
0x180078095  js      loc_1800782D6
0x18007809b  lea     r9d, [rbx+13h]
0x18007809f  mov     r8d, esi
0x1800780a2  lea     rdx, [rbp+57h+var_40]
0x1800780a6  lea     rcx, qword_18004A148
0x1800780ad  call    cs:__imp_RtlInitializeSidEx
0x1800780b4  nop     dword ptr [rax+rax+00h]
0x1800780b9  test    eax, eax
0x1800780bb  js      loc_1800782D6
0x1800780c1  lea     r9d, [rbx+14h]
0x1800780c5  mov     r8d, esi
0x1800780c8  lea     rdx, [rbp+57h+var_40]
0x1800780cc  lea     rcx, dword_18004A18C
0x1800780d3  call    cs:__imp_RtlInitializeSidEx
0x1800780da  nop     dword ptr [rax+rax+00h]
0x1800780df  test    eax, eax
0x1800780e1  js      loc_1800782D6
0x1800780e7  lea     esi, [rbx+20h]
0x1800780ea  mov     dword ptr [rsp+0A0h+var_80], 220h
0x1800780f2  mov     r9d, esi
0x1800780f5  lea     rdx, [rbp+57h+var_40]
0x1800780f9  mov     r8d, edi
0x1800780fc  lea     rcx, qword_18004A1D0
0x180078103  call    cs:__imp_RtlInitializeSidEx
0x18007810a  nop     dword ptr [rax+rax+00h]
0x18007810f  test    eax, eax
0x180078111  js      loc_1800782D6
0x180078117  mov     r9d, esi
0x18007811a  mov     dword ptr [rsp+0A0h+var_80], 252h
0x180078122  mov     r8d, edi
0x180078125  lea     rdx, [rbp+57h+var_40]
0x180078129  lea     rcx, dword_18004A214
0x180078130  call    cs:__imp_RtlInitializeSidEx
0x180078137  nop     dword ptr [rax+rax+00h]
0x18007813c  test    eax, eax
0x18007813e  js      loc_1800782D6
0x180078144  mov     r9d, esi
0x180078147  mov     dword ptr [rsp+0A0h+var_80], 226h
0x18007814f  mov     r8d, edi
0x180078152  lea     rdx, [rbp+57h+var_40]
0x180078156  lea     rcx, qword_18004A258
0x18007815d  call    cs:__imp_RtlInitializeSidEx
0x180078164  nop     dword ptr [rax+rax+00h]
0x180078169  test    eax, eax
0x18007816b  js      loc_1800782D6
0x180078171  mov     r9d, esi
0x180078174  mov     dword ptr [rsp+0A0h+var_80], 227h
0x18007817c  mov     r8d, edi
0x18007817f  lea     rdx, [rbp+57h+var_40]
0x180078183  lea     rcx, dword_18004A29C
0x18007818a  call    cs:__imp_RtlInitializeSidEx
0x180078191  nop     dword ptr [rax+rax+00h]
0x180078196  test    eax, eax
0x180078198  js      loc_1800782D6
0x18007819e  mov     r9d, esi
0x1800781a1  mov     dword ptr [rsp+0A0h+var_80], 241h
0x1800781a9  mov     r8d, edi
0x1800781ac  lea     rdx, [rbp+57h+var_40]
0x1800781b0  lea     rcx, qword_18004A2E0
0x1800781b7  call    cs:__imp_RtlInitializeSidEx
0x1800781be  nop     dword ptr [rax+rax+00h]
0x1800781c3  test    eax, eax
0x1800781c5  js      loc_1800782D6
0x1800781cb  mov     r9d, esi
0x1800781ce  mov     dword ptr [rsp+0A0h+var_80], 22Fh
0x1800781d6  mov     r8d, edi
0x1800781d9  lea     rdx, [rbp+57h+var_40]
0x1800781dd  lea     rcx, dword_18004A324
0x1800781e4  call    cs:__imp_RtlInitializeSidEx
0x1800781eb  nop     dword ptr [rax+rax+00h]
0x1800781f0  test    eax, eax
0x1800781f2  js      loc_1800782D6
0x1800781f8  mov     r9d, esi
0x1800781fb  mov     dword ptr [rsp+0A0h+var_80], 238h
0x180078203  mov     r8d, edi
0x180078206  lea     rdx, [rbp+57h+var_40]
0x18007820a  lea     rcx, qword_18004A368
0x180078211  call    cs:__imp_RtlInitializeSidEx
0x180078218  nop     dword ptr [rax+rax+00h]
0x18007821d  test    eax, eax
0x18007821f  js      loc_1800782D6
0x180078225  mov     [rsp+0A0h+var_50], 4C2B8C5Ah
0x18007822d  lea     esi, [rbx+8]
0x180078230  mov     [rsp+0A0h+var_58], 0F28A92BCh
0x180078238  lea     rdx, [rbp+57h+var_38]
0x18007823c  mov     [rsp+0A0h+var_60], 4767CC4Fh
0x180078244  lea     rcx, dword_18004A3AC
0x18007824b  mov     [rsp+0A0h+var_68], 1A2FA379h
0x180078253  mov     r9d, edi
0x180078256  mov     [rsp+0A0h+var_70], 3A0B3827h
0x18007825e  mov     r8d, esi
0x180078261  mov     [rsp+0A0h+var_78], 9D4F738Eh
0x180078269  mov     dword ptr [rsp+0A0h+var_80], 5542E9D2h
0x180078271  call    cs:__imp_RtlInitializeSidEx
0x180078278  nop     dword ptr [rax+rax+00h]
0x18007827d  test    eax, eax
0x18007827f  js      short loc_1800782D6
0x180078281  mov     [rsp+0A0h+var_50], 0A3B6F52Bh
0x180078289  lea     rdx, [rbp+57h+var_38]
0x18007828d  mov     [rsp+0A0h+var_58], 1A7CAEBBh
0x180078295  lea     rcx, qword_18004A3F0
0x18007829c  mov     [rsp+0A0h+var_60], 64782BBFh
0x1800782a4  mov     r9d, edi
0x1800782a7  mov     [rsp+0A0h+var_68], 0E5B1155Bh
0x1800782af  mov     r8d, esi
0x1800782b2  mov     [rsp+0A0h+var_70], 79318273h
0x1800782ba  mov     [rsp+0A0h+var_78], 1D02DE5Ch
0x1800782c2  mov     dword ptr [rsp+0A0h+var_80], 5B4DCD8h
0x1800782ca  call    cs:__imp_RtlInitializeSidEx
0x1800782d1  nop     dword ptr [rax+rax+00h]
0x1800782d6  mov     rcx, [rbp+57h+var_28]
0x1800782da  xor     rcx, rsp; StackCookie
0x1800782dd  call    __security_check_cookie
0x1800782e2  add     rsp, 88h
0x1800782e9  pop     rdi
0x1800782ea  pop     rsi
0x1800782eb  pop     rbx
0x1800782ec  pop     rbp
0x1800782ed  retn
```
