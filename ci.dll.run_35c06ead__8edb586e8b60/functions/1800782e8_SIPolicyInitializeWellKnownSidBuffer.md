# SIPolicyInitializeWellKnownSidBuffer

- ea: `0x1800782e8`
- end: `0x1800785cf`
- name: `SIPolicyInitializeWellKnownSidBuffer`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800e5228`

## callees

- `0x18002c0d0`
- `0x1800782e8`

## import_xrefs

- `ntoskrnl!RtlInitializeSidEx` at `0x18007833e`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078367`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007838d`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800783b3`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800783e3`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078410`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007843d`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007846a`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078497`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800784c4`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800784f1`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078551`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800785aa`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007833e`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078367`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007838d`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800783b3`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800783e3`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078410`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007843d`
- `ntoskrnl!RtlInitializeSidEx` at `0x18007846a`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078497`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800784c4`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800784f1`
- `ntoskrnl!RtlInitializeSidEx` at `0x180078551`
- `ntoskrnl!RtlInitializeSidEx` at `0x1800785aa`

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
    result = RtlInitializeSidEx(&dword_18004A124, &v13, 1, 18, v1);
    if ( (int)result >= 0 )
    {
      result = RtlInitializeSidEx(qword_18004A168, &v13, 1, 19, v2);
      if ( (int)result >= 0 )
      {
        result = RtlInitializeSidEx(&dword_18004A1AC, &v13, 1, 20, v3);
        if ( (int)result >= 0 )
        {
          LODWORD(v4) = 544;
          result = RtlInitializeSidEx(qword_18004A1F0, &v13, 2, 32, v4);
          if ( (int)result >= 0 )
          {
            LODWORD(v5) = 594;
            result = RtlInitializeSidEx(&dword_18004A234, &v13, 2, 32, v5);
            if ( (int)result >= 0 )
            {
              LODWORD(v6) = 550;
              result = RtlInitializeSidEx(qword_18004A278, &v13, 2, 32, v6);
              if ( (int)result >= 0 )
              {
                LODWORD(v7) = 551;
                result = RtlInitializeSidEx(&dword_18004A2BC, &v13, 2, 32, v7);
                if ( (int)result >= 0 )
                {
                  LODWORD(v8) = 577;
                  result = RtlInitializeSidEx(qword_18004A300, &v13, 2, 32, v8);
                  if ( (int)result >= 0 )
                  {
                    LODWORD(v9) = 559;
                    result = RtlInitializeSidEx(&dword_18004A344, &v13, 2, 32, v9);
                    if ( (int)result >= 0 )
                    {
                      LODWORD(v10) = 568;
                      result = RtlInitializeSidEx(qword_18004A388, &v13, 2, 32, v10);
                      if ( (int)result >= 0 )
                      {
                        LODWORD(v11) = 1430448594;
                        result = RtlInitializeSidEx(&dword_18004A3CC, &v15, 8, 2, v11);
                        if ( (int)result >= 0 )
                        {
                          LODWORD(v12) = 95739096;
                          return RtlInitializeSidEx(qword_18004A410, &v15, 8, 2, v12);
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
0x1800782e8  push    rbp
0x1800782ea  push    rbx
0x1800782eb  push    rsi
0x1800782ec  push    rdi
0x1800782ed  lea     rbp, [rsp-3Fh]
0x1800782f2  sub     rsp, 88h
0x1800782f9  mov     rax, cs:__security_cookie
0x180078300  xor     rax, rsp
0x180078303  mov     [rbp+57h+var_28], rax
0x180078307  xor     ebx, ebx
0x180078309  mov     [rbp+57h+var_2C], 300h
0x18007830f  lea     rdx, [rbp+57h+var_30]
0x180078313  mov     [rbp+57h+var_30], ebx
0x180078316  lea     rcx, g_SIPolicyWellKnownSids
0x18007831d  mov     [rbp+57h+var_40], ebx
0x180078320  mov     [rbp+57h+var_3C], 500h
0x180078326  lea     edi, [rbx+2]
0x180078329  mov     [rbp+57h+var_38], ebx
0x18007832c  mov     r8d, edi
0x18007832f  mov     [rbp+57h+var_34], 0F00h
0x180078335  lea     r9d, [rbx+3]
0x180078339  mov     [rsp+0A0h+var_80], rbx
0x18007833e  call    cs:__imp_RtlInitializeSidEx
0x180078345  nop     dword ptr [rax+rax+00h]
0x18007834a  test    eax, eax
0x18007834c  js      loc_1800785B6
0x180078352  lea     esi, [rbx+1]
0x180078355  mov     r8d, esi
0x180078358  lea     r9d, [rbx+12h]
0x18007835c  lea     rdx, [rbp+57h+var_40]
0x180078360  lea     rcx, dword_18004A124
0x180078367  call    cs:__imp_RtlInitializeSidEx
0x18007836e  nop     dword ptr [rax+rax+00h]
0x180078373  test    eax, eax
0x180078375  js      loc_1800785B6
0x18007837b  lea     r9d, [rbx+13h]
0x18007837f  mov     r8d, esi
0x180078382  lea     rdx, [rbp+57h+var_40]
0x180078386  lea     rcx, qword_18004A168
0x18007838d  call    cs:__imp_RtlInitializeSidEx
0x180078394  nop     dword ptr [rax+rax+00h]
0x180078399  test    eax, eax
0x18007839b  js      loc_1800785B6
0x1800783a1  lea     r9d, [rbx+14h]
0x1800783a5  mov     r8d, esi
0x1800783a8  lea     rdx, [rbp+57h+var_40]
0x1800783ac  lea     rcx, dword_18004A1AC
0x1800783b3  call    cs:__imp_RtlInitializeSidEx
0x1800783ba  nop     dword ptr [rax+rax+00h]
0x1800783bf  test    eax, eax
0x1800783c1  js      loc_1800785B6
0x1800783c7  lea     esi, [rbx+20h]
0x1800783ca  mov     dword ptr [rsp+0A0h+var_80], 220h
0x1800783d2  mov     r9d, esi
0x1800783d5  lea     rdx, [rbp+57h+var_40]
0x1800783d9  mov     r8d, edi
0x1800783dc  lea     rcx, qword_18004A1F0
0x1800783e3  call    cs:__imp_RtlInitializeSidEx
0x1800783ea  nop     dword ptr [rax+rax+00h]
0x1800783ef  test    eax, eax
0x1800783f1  js      loc_1800785B6
0x1800783f7  mov     r9d, esi
0x1800783fa  mov     dword ptr [rsp+0A0h+var_80], 252h
0x180078402  mov     r8d, edi
0x180078405  lea     rdx, [rbp+57h+var_40]
0x180078409  lea     rcx, dword_18004A234
0x180078410  call    cs:__imp_RtlInitializeSidEx
0x180078417  nop     dword ptr [rax+rax+00h]
0x18007841c  test    eax, eax
0x18007841e  js      loc_1800785B6
0x180078424  mov     r9d, esi
0x180078427  mov     dword ptr [rsp+0A0h+var_80], 226h
0x18007842f  mov     r8d, edi
0x180078432  lea     rdx, [rbp+57h+var_40]
0x180078436  lea     rcx, qword_18004A278
0x18007843d  call    cs:__imp_RtlInitializeSidEx
0x180078444  nop     dword ptr [rax+rax+00h]
0x180078449  test    eax, eax
0x18007844b  js      loc_1800785B6
0x180078451  mov     r9d, esi
0x180078454  mov     dword ptr [rsp+0A0h+var_80], 227h
0x18007845c  mov     r8d, edi
0x18007845f  lea     rdx, [rbp+57h+var_40]
0x180078463  lea     rcx, dword_18004A2BC
0x18007846a  call    cs:__imp_RtlInitializeSidEx
0x180078471  nop     dword ptr [rax+rax+00h]
0x180078476  test    eax, eax
0x180078478  js      loc_1800785B6
0x18007847e  mov     r9d, esi
0x180078481  mov     dword ptr [rsp+0A0h+var_80], 241h
0x180078489  mov     r8d, edi
0x18007848c  lea     rdx, [rbp+57h+var_40]
0x180078490  lea     rcx, qword_18004A300
0x180078497  call    cs:__imp_RtlInitializeSidEx
0x18007849e  nop     dword ptr [rax+rax+00h]
0x1800784a3  test    eax, eax
0x1800784a5  js      loc_1800785B6
0x1800784ab  mov     r9d, esi
0x1800784ae  mov     dword ptr [rsp+0A0h+var_80], 22Fh
0x1800784b6  mov     r8d, edi
0x1800784b9  lea     rdx, [rbp+57h+var_40]
0x1800784bd  lea     rcx, dword_18004A344
0x1800784c4  call    cs:__imp_RtlInitializeSidEx
0x1800784cb  nop     dword ptr [rax+rax+00h]
0x1800784d0  test    eax, eax
0x1800784d2  js      loc_1800785B6
0x1800784d8  mov     r9d, esi
0x1800784db  mov     dword ptr [rsp+0A0h+var_80], 238h
0x1800784e3  mov     r8d, edi
0x1800784e6  lea     rdx, [rbp+57h+var_40]
0x1800784ea  lea     rcx, qword_18004A388
0x1800784f1  call    cs:__imp_RtlInitializeSidEx
0x1800784f8  nop     dword ptr [rax+rax+00h]
0x1800784fd  test    eax, eax
0x1800784ff  js      loc_1800785B6
0x180078505  mov     [rsp+0A0h+var_50], 4C2B8C5Ah
0x18007850d  lea     esi, [rbx+8]
0x180078510  mov     [rsp+0A0h+var_58], 0F28A92BCh
0x180078518  lea     rdx, [rbp+57h+var_38]
0x18007851c  mov     [rsp+0A0h+var_60], 4767CC4Fh
0x180078524  lea     rcx, dword_18004A3CC
0x18007852b  mov     [rsp+0A0h+var_68], 1A2FA379h
0x180078533  mov     r9d, edi
0x180078536  mov     [rsp+0A0h+var_70], 3A0B3827h
0x18007853e  mov     r8d, esi
0x180078541  mov     [rsp+0A0h+var_78], 9D4F738Eh
0x180078549  mov     dword ptr [rsp+0A0h+var_80], 5542E9D2h
0x180078551  call    cs:__imp_RtlInitializeSidEx
0x180078558  nop     dword ptr [rax+rax+00h]
0x18007855d  test    eax, eax
0x18007855f  js      short loc_1800785B6
0x180078561  mov     [rsp+0A0h+var_50], 0A3B6F52Bh
0x180078569  lea     rdx, [rbp+57h+var_38]
0x18007856d  mov     [rsp+0A0h+var_58], 1A7CAEBBh
0x180078575  lea     rcx, qword_18004A410
0x18007857c  mov     [rsp+0A0h+var_60], 64782BBFh
0x180078584  mov     r9d, edi
0x180078587  mov     [rsp+0A0h+var_68], 0E5B1155Bh
0x18007858f  mov     r8d, esi
0x180078592  mov     [rsp+0A0h+var_70], 79318273h
0x18007859a  mov     [rsp+0A0h+var_78], 1D02DE5Ch
0x1800785a2  mov     dword ptr [rsp+0A0h+var_80], 5B4DCD8h
0x1800785aa  call    cs:__imp_RtlInitializeSidEx
0x1800785b1  nop     dword ptr [rax+rax+00h]
0x1800785b6  mov     rcx, [rbp+57h+var_28]
0x1800785ba  xor     rcx, rsp; StackCookie
0x1800785bd  call    __security_check_cookie
0x1800785c2  add     rsp, 88h
0x1800785c9  pop     rdi
0x1800785ca  pop     rsi
0x1800785cb  pop     rbx
0x1800785cc  pop     rbp
0x1800785cd  retn
```
