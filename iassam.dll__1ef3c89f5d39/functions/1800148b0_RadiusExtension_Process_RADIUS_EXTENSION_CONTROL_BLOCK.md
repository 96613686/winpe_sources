# RadiusExtension::Process(_RADIUS_EXTENSION_CONTROL_BLOCK *)

- ea: `0x1800148b0`
- end: `0x180014b53`
- name: `?Process@RadiusExtension@@QEBAKPEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `675`
- prototype: `unsigned int(RadiusExtension *__hidden this, struct _RADIUS_EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001247c`

## callees

- `0x18000c500`
- `0x18000e754`
- `0x1800143d4`
- `0x1800144f8`
- `0x1800148b0`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!free` at `0x180014ab8`
- `msvcrt!free` at `0x180014ab8`

## string_xrefs

- `0x1800148e8`: `Invoking extension %S`
- `0x180014945`: `RadiusExtensionProcess2 returned %lu`
- `0x180014a4a`: `RadiusExtensionProcessEx returned %lu`
- `0x180014a89`: `RadiusExtensionProcess returned %lu`

## pseudocode

```c
__int64 __fastcall RadiusExtension::Process(RadiusExtension *this, struct _RADIUS_EXTENSION_CONTROL_BLOCK *a2)
{
  int v4; // r9d
  __int64 (__fastcall *v5)(struct _RADIUS_EXTENSION_CONTROL_BLOCK *); // rax
  unsigned int v6; // ebx
  int v8; // r14d
  int v9; // ecx
  unsigned int v10; // esi
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  struct _RADIUS_ATTRIBUTE *ExtensionAttributes; // rax
  struct _RADIUS_ATTRIBUTE *v15; // rbp
  __int64 (__fastcall *v16)(struct _RADIUS_ATTRIBUTE *, _DWORD **, unsigned __int64); // rax
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rsi
  _DWORD *v20; // rbx
  int v21; // [rsp+60h] [rbp+8h] BYREF
  _DWORD *v22; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Invoking extension %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids,
      v4,
      *(_QWORD *)this);
  }
  v5 = (__int64 (__fastcall *)(struct _RADIUS_EXTENSION_CONTROL_BLOCK *))*((_QWORD *)this + 8);
  if ( !v5 )
  {
    v8 = 0;
    v9 = LOWORD(a2->repPoint) | (LOWORD(a2->rcResponseType) << 16);
    v10 = 2;
    if ( v9 )
    {
      v11 = v9 - 1;
      if ( v11 )
      {
        v12 = v11 - 0x20000;
        if ( v12 )
        {
          v13 = v12 - 196607;
          if ( v13 )
          {
            if ( v13 != 1 )
              return 0;
            goto LABEL_18;
          }
LABEL_21:
          ExtensionAttributes = RadiusExtension::CreateExtensionAttributes(a2);
LABEL_22:
          v15 = ExtensionAttributes;
          if ( !ExtensionAttributes )
            return 8;
          v22 = 0;
          v21 = 0;
          v16 = (__int64 (__fastcall *)(struct _RADIUS_ATTRIBUTE *, _DWORD **, unsigned __int64))*((_QWORD *)this + 6);
          if ( v16 )
          {
            v17 = v16(v15, &v22, (unsigned __int64)&v21 & -(__int64)(v8 != 0));
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("RadiusExtensionProcessEx returned %lu");
              v18 = 17;
LABEL_33:
              WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids);
            }
          }
          else
          {
            v17 = (*((__int64 (__fastcall **)(struct _RADIUS_ATTRIBUTE *, unsigned __int64))this + 5))(
                    v15,
                    (unsigned __int64)&v21 & -(__int64)(v8 != 0));
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("RadiusExtensionProcess returned %lu");
              v18 = 18;
              goto LABEL_33;
            }
          }
          free(v15);
          if ( v17 )
            return v17;
          if ( v21 == 2 )
          {
            if ( (v8 & 1) == 0 )
              goto LABEL_42;
          }
          else
          {
            if ( v21 != 1 || (v8 & 2) == 0 )
            {
LABEL_42:
              if ( v22 )
              {
                v19 = ((__int64 (__fastcall *)(struct _RADIUS_EXTENSION_CONTROL_BLOCK *, _QWORD))a2->GetResponse)(
                        a2,
                        v10);
                v20 = v22;
                if ( *v22 )
                {
                  do
                  {
                    v17 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(v19 + 8))(v19, v20);
                    if ( v17 )
                      break;
                    v20 += 6;
                  }
                  while ( *v20 );
                  v20 = v22;
                }
                (*((void (__fastcall **)(_DWORD *))this + 7))(v20);
              }
              return v17;
            }
            v10 = 3;
          }
          ((void (__fastcall *)(struct _RADIUS_EXTENSION_CONTROL_BLOCK *, _QWORD))a2->SetResponseType)(a2, v10);
          goto LABEL_42;
        }
        v8 = 2;
      }
      else
      {
        ((void (__fastcall *)(struct _RADIUS_EXTENSION_CONTROL_BLOCK *, __int64))a2->SetResponseType)(a2, 5);
      }
LABEL_18:
      ExtensionAttributes = RadiusExtension::CreateAuthorizationAttributes(a2);
      goto LABEL_22;
    }
    v8 = 3;
    goto LABEL_21;
  }
  v6 = v5(a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("RadiusExtensionProcess2 returned %lu");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1800148b0  mov     [rsp+arg_8], rbx
0x1800148b5  push    rbp
0x1800148b6  push    rsi
0x1800148b7  push    rdi
0x1800148b8  push    r14
0x1800148ba  push    r15
0x1800148bc  sub     rsp, 30h
0x1800148c0  mov     rbx, rdx
0x1800148c3  mov     r15, rcx
0x1800148c6  lea     rdi, WPP_GLOBAL_Control
0x1800148cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800148d4  cmp     rax, rdi
0x1800148d7  jz      short loc_180014918
0x1800148d9  cmp     byte ptr [rax+19h], 4
0x1800148dd  jb      short loc_180014918
0x1800148df  test    byte ptr [rax+1Ch], 4
0x1800148e3  jz      short loc_180014918
0x1800148e5  mov     rdx, [rcx]
0x1800148e8  lea     rcx, aInvokingExtens; "Invoking extension %S"
0x1800148ef  call    WppDbgPrint
0x1800148f4  mov     edx, 0Fh
0x1800148f9  mov     rax, [r15]
0x1800148fc  mov     [rsp+58h+var_38], rax
0x180014901  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014908  mov     rcx, cs:WPP_GLOBAL_Control
0x18001490f  mov     rcx, [rcx+10h]
0x180014913  call    WPP_SF_sS
0x180014918  mov     rax, [r15+40h]
0x18001491c  test    rax, rax
0x18001491f  jz      short loc_180014978
0x180014921  mov     rcx, rbx
0x180014924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014929  mov     ebx, eax
0x18001492b  mov     rax, cs:WPP_GLOBAL_Control
0x180014932  cmp     rax, rdi
0x180014935  jz      short loc_180014971
0x180014937  cmp     byte ptr [rax+19h], 4
0x18001493b  jb      short loc_180014971
0x18001493d  test    byte ptr [rax+1Ch], 4
0x180014941  jz      short loc_180014971
0x180014943  mov     edx, ebx
0x180014945  lea     rcx, aRadiusextensio_3; "RadiusExtensionProcess2 returned %lu"
0x18001494c  call    WppDbgPrint
0x180014951  mov     edx, 10h
0x180014956  mov     dword ptr [rsp+58h+var_38], ebx
0x18001495a  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014961  mov     rcx, cs:WPP_GLOBAL_Control
0x180014968  mov     rcx, [rcx+10h]
0x18001496c  call    WPP_SF_sd
0x180014971  mov     eax, ebx
0x180014973  jmp     loc_180014B42
0x180014978  xor     r14d, r14d
0x18001497b  movzx   ecx, word ptr [rbx+10h]
0x18001497f  shl     ecx, 10h
0x180014982  movzx   eax, word ptr [rbx+8]
0x180014986  or      ecx, eax
0x180014988  lea     esi, [r14+2]
0x18001498c  jz      short loc_1800149CF
0x18001498e  sub     ecx, 1
0x180014991  jz      short loc_1800149BC
0x180014993  sub     ecx, 20000h
0x180014999  jz      short loc_1800149AF
0x18001499b  sub     ecx, 2FFFFh
0x1800149a1  jz      short loc_1800149D5
0x1800149a3  cmp     ecx, 1
0x1800149a6  jz      short loc_1800149B2
0x1800149a8  xor     eax, eax
0x1800149aa  jmp     loc_180014B42
0x1800149af  mov     r14d, esi
0x1800149b2  mov     rcx, rbx; struct _RADIUS_EXTENSION_CONTROL_BLOCK *
0x1800149b5  call    ?CreateAuthorizationAttributes@RadiusExtension@@CAPEAU_RADIUS_ATTRIBUTE@@PEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@@Z; RadiusExtension::CreateAuthorizationAttributes(_RADIUS_EXTENSION_CONTROL_BLOCK *)
0x1800149ba  jmp     short loc_1800149DD
0x1800149bc  mov     edx, 5
0x1800149c1  mov     rcx, rbx
0x1800149c4  mov     rax, [rbx+28h]
0x1800149c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149cd  jmp     short loc_1800149B2
0x1800149cf  mov     r14d, 3
0x1800149d5  mov     rcx, rbx; struct _RADIUS_EXTENSION_CONTROL_BLOCK *
0x1800149d8  call    ?CreateExtensionAttributes@RadiusExtension@@CAPEAU_RADIUS_ATTRIBUTE@@PEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@@Z; RadiusExtension::CreateExtensionAttributes(_RADIUS_EXTENSION_CONTROL_BLOCK *)
0x1800149dd  mov     rbp, rax
0x1800149e0  test    rax, rax
0x1800149e3  jnz     short loc_1800149ED
0x1800149e5  lea     eax, [rbp+8]
0x1800149e8  jmp     loc_180014B42
0x1800149ed  mov     [rsp+58h+arg_10], 0
0x1800149f6  mov     [rsp+58h+arg_0], 0
0x1800149fe  mov     eax, r14d
0x180014a01  neg     eax
0x180014a03  sbb     rdx, rdx
0x180014a06  lea     rax, [rsp+58h+arg_0]
0x180014a0b  and     rdx, rax
0x180014a0e  mov     rax, [r15+30h]
0x180014a12  mov     rcx, rbp
0x180014a15  test    rax, rax
0x180014a18  jz      short loc_180014A5D
0x180014a1a  mov     r8, rdx
0x180014a1d  lea     rdx, [rsp+58h+arg_10]
0x180014a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a27  mov     edi, eax
0x180014a29  mov     rax, cs:WPP_GLOBAL_Control
0x180014a30  lea     rcx, WPP_GLOBAL_Control
0x180014a37  cmp     rax, rcx
0x180014a3a  jz      short loc_180014AB5
0x180014a3c  cmp     byte ptr [rax+19h], 4
0x180014a40  jb      short loc_180014AB5
0x180014a42  test    byte ptr [rax+1Ch], 4
0x180014a46  jz      short loc_180014AB5
0x180014a48  mov     edx, edi
0x180014a4a  lea     rcx, aRadiusextensio_5; "RadiusExtensionProcessEx returned %lu"
0x180014a51  call    WppDbgPrint
0x180014a56  mov     edx, 11h
0x180014a5b  jmp     short loc_180014A9A
0x180014a5d  mov     rax, [r15+28h]
0x180014a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a66  mov     edi, eax
0x180014a68  mov     rax, cs:WPP_GLOBAL_Control
0x180014a6f  lea     rcx, WPP_GLOBAL_Control
0x180014a76  cmp     rax, rcx
0x180014a79  jz      short loc_180014AB5
0x180014a7b  cmp     byte ptr [rax+19h], 4
0x180014a7f  jb      short loc_180014AB5
0x180014a81  test    byte ptr [rax+1Ch], 4
0x180014a85  jz      short loc_180014AB5
0x180014a87  mov     edx, edi
0x180014a89  lea     rcx, aRadiusextensio_9; "RadiusExtensionProcess returned %lu"
0x180014a90  call    WppDbgPrint
0x180014a95  mov     edx, 12h
0x180014a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aa1  mov     dword ptr [rsp+58h+var_38], edi
0x180014aa5  lea     r8, WPP_b461da539d613e66bfc4a53e3ac78614_Traceguids
0x180014aac  mov     rcx, [rcx+10h]
0x180014ab0  call    WPP_SF_sd
0x180014ab5  mov     rcx, rbp; Block
0x180014ab8  call    cs:__imp_free
0x180014abe  test    edi, edi
0x180014ac0  jnz     short loc_180014B40
0x180014ac2  cmp     [rsp+58h+arg_0], esi
0x180014ac6  jnz     short loc_180014AD0
0x180014ac8  test    r14b, 1
0x180014acc  jz      short loc_180014AEF
0x180014ace  jmp     short loc_180014AE1
0x180014ad0  cmp     [rsp+58h+arg_0], 1
0x180014ad5  jnz     short loc_180014AEF
0x180014ad7  test    sil, r14b
0x180014ada  jz      short loc_180014AEF
0x180014adc  mov     esi, 3
0x180014ae1  mov     edx, esi
0x180014ae3  mov     rcx, rbx
0x180014ae6  mov     rax, [rbx+28h]
0x180014aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aef  cmp     [rsp+58h+arg_10], 0
0x180014af5  jz      short loc_180014B40
0x180014af7  mov     edx, esi
0x180014af9  mov     rcx, rbx
0x180014afc  mov     rax, [rbx+20h]
0x180014b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b05  mov     rsi, rax
0x180014b08  mov     rbx, [rsp+58h+arg_10]
0x180014b0d  cmp     dword ptr [rbx], 0
0x180014b10  jz      short loc_180014B34
0x180014b12  mov     rdx, rbx
0x180014b15  mov     rcx, rsi
0x180014b18  mov     rax, [rsi+8]
0x180014b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b21  mov     edi, eax
0x180014b23  test    eax, eax
0x180014b25  jnz     short loc_180014B2F
0x180014b27  add     rbx, 18h
0x180014b2b  cmp     [rbx], eax
0x180014b2d  jnz     short loc_180014B12
0x180014b2f  mov     rbx, [rsp+58h+arg_10]
0x180014b34  mov     rcx, rbx
0x180014b37  mov     rax, [r15+38h]
0x180014b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b40  mov     eax, edi
0x180014b42  mov     rbx, [rsp+58h+arg_8]
0x180014b47  add     rsp, 30h
0x180014b4b  pop     r15
0x180014b4d  pop     r14
0x180014b4f  pop     rdi
0x180014b50  pop     rsi
0x180014b51  pop     rbp
0x180014b52  retn
```
