# CSendToPipe::TraceNapAttributes(IAttributesRaw *)

- ea: `0x180019340`
- end: `0x180019675`
- name: `?TraceNapAttributes@CSendToPipe@@QEAAJPEAUIAttributesRaw@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(CSendToPipe *__hidden this, struct IAttributesRaw *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018ca4`

## callees

- `0x1800094e4`
- `0x18000dc54`
- `0x180019340`
- `0x18001d31c`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001965f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001965f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019464`

## string_xrefs

- `0x180019580`: `An access request message containing NAP attributes was received, This attributes will be ignored because NAP is not supported by this operating system.`

## pseudocode

```c
__int64 __fastcall CSendToPipe::TraceNapAttributes(CSendToPipe *this, struct IAttributesRaw *a2)
{
  unsigned int v3; // r12d
  _QWORD *v4; // r14
  int v5; // esi
  __int64 v6; // rdx
  unsigned int v7; // ecx
  PVOID *v8; // rax
  unsigned int i; // r15d
  unsigned int j; // ebx
  unsigned int v12; // [rsp+90h] [rbp+8h] BYREF
  int v13; // [rsp+94h] [rbp+Ch]

  v13 = HIDWORD(this);
  v3 = 0;
  v4 = 0;
  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *))(*(_QWORD *)a2 + 48LL))(a2, &v12);
  if ( v5 >= 0 )
  {
    if ( v12 )
    {
      if ( v12 <= 0xFFFFFFF )
      {
        v4 = CoTaskMemAlloc(16LL * v12);
        if ( v4 )
        {
          v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *, _QWORD *, __int64, __int64 *))(*(_QWORD *)a2 + 56LL))(
                 a2,
                 &v12,
                 v4,
                 7,
                 qword_180041548);
          if ( v5 >= 0 )
          {
            v7 = v12;
            if ( v12 )
            {
              v3 = v12;
              v8 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WppDbgPrint("An access request message containing NAP attributes was received, This attributes will be ig"
                            "nored because NAP is not supported by this operating system.");
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids,
                  "NPSRAD");
                v7 = v12;
                v8 = (PVOID *)WPP_GLOBAL_Control;
              }
              for ( i = 0; i < v7; ++i )
              {
                if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 5u && (*((_DWORD *)v8 + 7) & 0x100) != 0 )
                {
                  WppDbgPrint("Attribute ID: %d");
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    22,
                    (unsigned int)WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids,
                    (unsigned int)"NPSRAD",
                    *(_DWORD *)(v4[2 * i + 1] + 8LL));
                  v7 = v12;
                  v8 = (PVOID *)WPP_GLOBAL_Control;
                }
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to obtain information about attributeswhile splitting attributes in out-bound RADIUS packet");
            v6 = 20;
            goto LABEL_6;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to allocate memory for attribute position array while splitting attributes in out-bound packet");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
          }
          v5 = -2147024882;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Large attribute count caused integer overflow");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
        }
        v5 = -2147024362;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to obtain attribute count in request while splitting attributes in out-bound packet ");
    v6 = 17;
LABEL_6:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
  }
  if ( v4 )
  {
    for ( j = 0; j < v3; ++j )
      IASAttributeRelease((LPVOID)v4[2 * j + 1]);
    CoTaskMemFree(v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019340  mov     r11, rsp
0x180019343  mov     [r11+8], rcx
0x180019347  push    rbx
0x180019348  push    rsi
0x180019349  push    rdi
0x18001934a  push    r12
0x18001934c  push    r14
0x18001934e  push    r15
0x180019350  sub     rsp, 58h
0x180019354  mov     rbx, rdx
0x180019357  xor     r12d, r12d
0x18001935a  mov     [r11-54h], r12d
0x18001935e  xor     r14d, r14d
0x180019361  mov     [r11-48h], r14
0x180019365  mov     [r11+8], r14d
0x180019369  mov     rax, [rdx]
0x18001936c  lea     rdx, [r11+8]
0x180019370  mov     rcx, rbx
0x180019373  mov     rax, [rax+30h]
0x180019377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001937c  mov     esi, eax
0x18001937e  mov     [rsp+88h+var_58], eax
0x180019382  test    eax, eax
0x180019384  jns     short loc_1800193E8
0x180019386  lea     rdi, WPP_GLOBAL_Control
0x18001938d  mov     rax, cs:WPP_GLOBAL_Control
0x180019394  cmp     rax, rdi
0x180019397  jz      loc_18001963A
0x18001939d  cmp     byte ptr [rax+19h], 2
0x1800193a1  jb      loc_18001963A
0x1800193a7  test    dword ptr [rax+1Ch], 100h
0x1800193ae  jz      loc_18001963A
0x1800193b4  lea     rcx, aUnableToObtain_5; "Unable to obtain attribute count in req"...
0x1800193bb  call    WppDbgPrint
0x1800193c0  lea     edx, [r12+11h]
0x1800193c5  lea     r9, aNpsrad; "NPSRAD"
0x1800193cc  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x1800193d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193da  mov     rcx, [rcx+10h]
0x1800193de  call    WPP_SF_s
0x1800193e3  jmp     loc_18001963A
0x1800193e8  mov     eax, [rsp+88h+arg_0]
0x1800193ef  test    eax, eax
0x1800193f1  jz      loc_18001963A
0x1800193f7  cmp     eax, 0FFFFFFFh
0x1800193fc  jbe     short loc_18001945D
0x1800193fe  lea     rdi, WPP_GLOBAL_Control
0x180019405  mov     rax, cs:WPP_GLOBAL_Control
0x18001940c  cmp     rax, rdi
0x18001940f  jz      short loc_18001944F
0x180019411  cmp     byte ptr [rax+19h], 2
0x180019415  jb      short loc_18001944F
0x180019417  test    dword ptr [rax+1Ch], 100h
0x18001941e  jz      short loc_18001944F
0x180019420  lea     rcx, aLargeAttribute; "Large attribute count caused integer ov"...
0x180019427  call    WppDbgPrint
0x18001942c  mov     edx, 12h
0x180019431  lea     r9, aNpsrad; "NPSRAD"
0x180019438  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x18001943f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019446  mov     rcx, [rcx+10h]
0x18001944a  call    WPP_SF_s
0x18001944f  mov     esi, 80070216h
0x180019454  mov     [rsp+88h+var_58], esi
0x180019458  jmp     loc_18001963A
0x18001945d  mov     rcx, rax
0x180019460  shl     rcx, 4; cb
0x180019464  call    cs:__imp_CoTaskMemAlloc
0x18001946a  mov     r14, rax
0x18001946d  mov     [rsp+88h+var_48], rax
0x180019472  test    rax, rax
0x180019475  jnz     short loc_1800194CE
0x180019477  lea     rdi, WPP_GLOBAL_Control
0x18001947e  mov     rax, cs:WPP_GLOBAL_Control
0x180019485  cmp     rax, rdi
0x180019488  jz      short loc_1800194C7
0x18001948a  cmp     byte ptr [rax+19h], 2
0x18001948e  jb      short loc_1800194C7
0x180019490  test    dword ptr [rax+1Ch], 100h
0x180019497  jz      short loc_1800194C7
0x180019499  lea     rcx, aUnableToAlloca_0; "Unable to allocate memory for attribute"...
0x1800194a0  call    WppDbgPrint
0x1800194a5  lea     edx, [r14+13h]
0x1800194a9  lea     r9, aNpsrad; "NPSRAD"
0x1800194b0  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x1800194b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194be  mov     rcx, [rcx+10h]
0x1800194c2  call    WPP_SF_s
0x1800194c7  mov     esi, 8007000Eh
0x1800194cc  jmp     short loc_180019454
0x1800194ce  mov     rax, [rbx]
0x1800194d1  lea     rcx, qword_180041548
0x1800194d8  mov     [rsp+88h+var_68], rcx
0x1800194dd  mov     r9d, 7
0x1800194e3  mov     r8, r14
0x1800194e6  lea     rdx, [rsp+88h+arg_0]
0x1800194ee  mov     rcx, rbx
0x1800194f1  mov     rax, [rax+38h]
0x1800194f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194fa  mov     esi, eax
0x1800194fc  mov     [rsp+88h+var_58], eax
0x180019500  test    eax, eax
0x180019502  jns     short loc_180019548
0x180019504  lea     rdi, WPP_GLOBAL_Control
0x18001950b  mov     rax, cs:WPP_GLOBAL_Control
0x180019512  cmp     rax, rdi
0x180019515  jz      loc_18001963A
0x18001951b  cmp     byte ptr [rax+19h], 2
0x18001951f  jb      loc_18001963A
0x180019525  test    dword ptr [rax+1Ch], 100h
0x18001952c  jz      loc_18001963A
0x180019532  lea     rcx, aUnableToObtain_8; "Unable to obtain information about attr"...
0x180019539  call    WppDbgPrint
0x18001953e  mov     edx, 14h
0x180019543  jmp     loc_1800193C5
0x180019548  mov     ecx, [rsp+88h+arg_0]
0x18001954f  test    ecx, ecx
0x180019551  jz      loc_18001963A
0x180019557  mov     r12d, ecx
0x18001955a  mov     [rsp+88h+var_54], ecx
0x18001955e  lea     rdi, WPP_GLOBAL_Control
0x180019565  mov     rax, cs:WPP_GLOBAL_Control
0x18001956c  cmp     rax, rdi
0x18001956f  jz      short loc_1800195BD
0x180019571  cmp     byte ptr [rax+19h], 5
0x180019575  jb      short loc_1800195BD
0x180019577  test    dword ptr [rax+1Ch], 100h
0x18001957e  jz      short loc_1800195BD
0x180019580  lea     rcx, aAnAccessReques; "An access request message containing NA"...
0x180019587  call    WppDbgPrint
0x18001958c  mov     edx, 15h
0x180019591  lea     r9, aNpsrad; "NPSRAD"
0x180019598  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x18001959f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195a6  mov     rcx, [rcx+10h]
0x1800195aa  call    WPP_SF_s
0x1800195af  mov     ecx, [rsp+88h+arg_0]
0x1800195b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800195bd  xor     r15d, r15d
0x1800195c0  mov     [rsp+88h+var_50], r15d
0x1800195c5  cmp     r15d, ecx
0x1800195c8  jnb     short loc_18001963A
0x1800195ca  cmp     rax, rdi
0x1800195cd  jz      short loc_180019635
0x1800195cf  cmp     byte ptr [rax+19h], 5
0x1800195d3  jb      short loc_180019635
0x1800195d5  test    dword ptr [rax+1Ch], 100h
0x1800195dc  jz      short loc_180019635
0x1800195de  mov     ebx, r15d
0x1800195e1  add     rbx, rbx
0x1800195e4  mov     rdx, [r14+rbx*8+8]
0x1800195e9  mov     edx, [rdx+8]
0x1800195ec  lea     rcx, aAttributeIdD; "Attribute ID: %d"
0x1800195f3  call    WppDbgPrint
0x1800195f8  mov     rax, [r14+rbx*8+8]
0x1800195fd  mov     edx, 16h
0x180019602  mov     eax, [rax+8]
0x180019605  mov     dword ptr [rsp+88h+var_68], eax
0x180019609  lea     r9, aNpsrad; "NPSRAD"
0x180019610  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x180019617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001961e  mov     rcx, [rcx+10h]
0x180019622  call    WPP_SF_sd
0x180019627  mov     ecx, [rsp+88h+arg_0]
0x18001962e  mov     rax, cs:WPP_GLOBAL_Control
0x180019635  inc     r15d
0x180019638  jmp     short loc_1800195C0
0x18001963a  test    r14, r14
0x18001963d  jz      short loc_180019665
0x18001963f  xor     ebx, ebx
0x180019641  test    r12d, r12d
0x180019644  jz      short loc_18001965C
0x180019646  mov     ecx, ebx
0x180019648  add     rcx, rcx
0x18001964b  mov     rcx, [r14+rcx*8+8]; pv
0x180019650  call    IASAttributeRelease
0x180019655  inc     ebx
0x180019657  cmp     ebx, r12d
0x18001965a  jb      short loc_180019646
0x18001965c  mov     rcx, r14; pv
0x18001965f  call    cs:__imp_CoTaskMemFree
0x180019665  mov     eax, esi
0x180019667  add     rsp, 58h
0x18001966b  pop     r15
0x18001966d  pop     r14
0x18001966f  pop     r12
0x180019671  pop     rdi
0x180019672  pop     rsi
0x180019673  pop     rbx
0x180019674  retn
0x18002f073  push    rbx
0x18002f075  push    rbp
0x18002f076  push    rsi
0x18002f077  push    rdi
0x18002f078  sub     rsp, 38h
0x18002f07c  mov     rbp, rdx
0x18002f07f  mov     rdi, [rbp+40h]
0x18002f083  test    rdi, rdi
0x18002f086  jz      short loc_18002F0B0
0x18002f088  xor     ebx, ebx
0x18002f08a  mov     esi, [rbp+34h]
0x18002f08d  test    esi, esi
0x18002f08f  jz      short loc_18002F0A6
0x18002f091  mov     ecx, ebx
0x18002f093  add     rcx, rcx
0x18002f096  mov     rcx, [rdi+rcx*8+8]; pv
0x18002f09b  call    IASAttributeRelease
0x18002f0a0  inc     ebx
0x18002f0a2  cmp     ebx, esi
0x18002f0a4  jb      short loc_18002F091
0x18002f0a6  mov     rcx, rdi; pv
0x18002f0a9  call    cs:__imp_CoTaskMemFree
0x18002f0af  nop
0x18002f0b0  add     rsp, 38h
0x18002f0b4  pop     rdi
0x18002f0b5  pop     rsi
0x18002f0b6  pop     rbp
0x18002f0b7  pop     rbx
0x18002f0b8  retn
```
