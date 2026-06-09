# CTunnelPassword::Process(_packettype_,IAttributesRaw *,CPacketRadius *)

- ea: `0x18001b898`
- end: `0x18001bb38`
- name: `?Process@CTunnelPassword@@QEAAJW4_packettype_@@PEAUIAttributesRaw@@PEAVCPacketRadius@@@Z`
- size: `672`
- prototype: `int __high(enum _packettype_, struct IAttributesRaw *, struct CPacketRadius *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800179a4`

## callees

- `0x1800094e4`
- `0x18001b4a0`
- `0x18001b758`
- `0x18001b898`
- `0x18001d31c`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b976`

## string_xrefs

- `0x18001baaf`: `Unable to remove attributes from request while processing tunnel-password`

## pseudocode

```c
__int64 __fastcall CTunnelPassword::Process(
        __int64 a1,
        __int64 a2,
        struct IAttributesRaw *a3,
        const struct CPacketRadius *a4)
{
  struct _IASATTRIBUTE **v6; // rdi
  int v7; // ebx
  __int64 v8; // rdx
  unsigned int i; // esi
  unsigned int j; // esi
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF

  v13 = HIDWORD(a1);
  v12 = 0;
  v14 = 0;
  v6 = 0;
  v7 = EncryptVSAs(a4, a3);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *))(*(_QWORD *)a3 + 48LL))(a3, &v12);
    if ( v7 >= 0 )
    {
      if ( v12 )
      {
        v6 = (struct _IASATTRIBUTE **)CoTaskMemAlloc(16LL * v12);
        if ( v6 )
        {
          v14 = v12;
          v7 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *, struct _IASATTRIBUTE **, __int64, int *))(*(_QWORD *)a3 + 56LL))(
                 a3,
                 &v14,
                 v6,
                 1,
                 &dword_180041564);
          if ( v7 >= 0 )
          {
            if ( v14 )
            {
              v7 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, _QWORD, struct _IASATTRIBUTE **))(*(_QWORD *)a3 + 32LL))(
                     a3,
                     v14,
                     v6);
              if ( v7 >= 0 )
              {
                for ( i = 0; i < v14; ++i )
                {
                  v7 = CTunnelPassword::EncryptTunnelPassword(a4, a3, v6[2 * i + 1]);
                  if ( v7 < 0 )
                    break;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                     && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WppDbgPrint("Unable to remove attributes from request while processing tunnel-password");
                v8 = 13;
                goto LABEL_7;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to get attributes from request while processing tunnel-password");
            v8 = 12;
            goto LABEL_7;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to allocate memory for attribute position array while processing tunnel-password");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
          }
          v7 = -2147024882;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain attribute count in request while processing tunnel-password");
      v8 = 10;
LABEL_7:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
    }
  }
  for ( j = 0; j < v14; ++j )
    IASAttributeRelease(v6[2 * j + 1]);
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b898  mov     rax, rsp
0x18001b89b  mov     [rax+18h], rbx
0x18001b89f  mov     [rax+20h], rsi
0x18001b8a3  mov     [rax+10h], edx
0x18001b8a6  mov     [rax+8], rcx
0x18001b8aa  push    rdi
0x18001b8ab  push    r14
0x18001b8ad  push    r15
0x18001b8af  sub     rsp, 40h
0x18001b8b3  mov     r15, r9
0x18001b8b6  mov     r14, r8
0x18001b8b9  mov     dword ptr [rax+8], 0
0x18001b8c0  mov     dword ptr [rax+10h], 0
0x18001b8c7  xor     edi, edi
0x18001b8c9  mov     [rax-20h], rdi
0x18001b8cd  mov     rdx, r8; struct IAttributesRaw *
0x18001b8d0  mov     rcx, r9; this
0x18001b8d3  call    ?EncryptVSAs@@YAJAEBVCPacketRadius@@PEAUIAttributesRaw@@@Z; EncryptVSAs(CPacketRadius const &,IAttributesRaw *)
0x18001b8d8  mov     ebx, eax
0x18001b8da  mov     [rsp+58h+var_28], eax
0x18001b8de  test    eax, eax
0x18001b8e0  js      loc_18001BAF5
0x18001b8e6  mov     rax, [r14]
0x18001b8e9  lea     rdx, [rsp+58h+arg_0]
0x18001b8ee  mov     rcx, r14
0x18001b8f1  mov     rax, [rax+30h]
0x18001b8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8fa  mov     ebx, eax
0x18001b8fc  mov     [rsp+58h+var_28], eax
0x18001b900  test    eax, eax
0x18001b902  jns     short loc_18001B964
0x18001b904  lea     rax, WPP_GLOBAL_Control
0x18001b90b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b912  cmp     rcx, rax
0x18001b915  jz      loc_18001BAF5
0x18001b91b  cmp     byte ptr [rcx+19h], 2
0x18001b91f  jb      loc_18001BAF5
0x18001b925  test    dword ptr [rcx+1Ch], 100h
0x18001b92c  jz      loc_18001BAF5
0x18001b932  lea     rcx, aUnableToObtain_16; "Unable to obtain attribute count in req"...
0x18001b939  call    WppDbgPrint
0x18001b93e  lea     edx, [rdi+0Ah]
0x18001b941  lea     r9, aNpsrad; "NPSRAD"
0x18001b948  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b956  mov     rcx, [rcx+10h]
0x18001b95a  call    WPP_SF_s
0x18001b95f  jmp     loc_18001BAF5
0x18001b964  mov     eax, [rsp+58h+arg_0]
0x18001b968  test    eax, eax
0x18001b96a  jz      loc_18001BAF5
0x18001b970  mov     ecx, eax
0x18001b972  shl     rcx, 4; cb
0x18001b976  call    cs:__imp_CoTaskMemAlloc
0x18001b97c  mov     rdi, rax
0x18001b97f  mov     [rsp+58h+var_20], rax
0x18001b984  test    rax, rax
0x18001b987  jnz     short loc_18001B9E6
0x18001b989  lea     rax, WPP_GLOBAL_Control
0x18001b990  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b997  cmp     rcx, rax
0x18001b99a  jz      short loc_18001B9D8
0x18001b99c  cmp     byte ptr [rcx+19h], 2
0x18001b9a0  jb      short loc_18001B9D8
0x18001b9a2  test    dword ptr [rcx+1Ch], 100h
0x18001b9a9  jz      short loc_18001B9D8
0x18001b9ab  lea     rcx, aUnableToAlloca_3; "Unable to allocate memory for attribute"...
0x18001b9b2  call    WppDbgPrint
0x18001b9b7  lea     edx, [rdi+0Bh]
0x18001b9ba  lea     r9, aNpsrad; "NPSRAD"
0x18001b9c1  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9cf  mov     rcx, [rcx+10h]
0x18001b9d3  call    WPP_SF_s
0x18001b9d8  mov     ebx, 8007000Eh
0x18001b9dd  mov     [rsp+58h+var_28], ebx
0x18001b9e1  jmp     loc_18001BAF5
0x18001b9e6  mov     eax, [rsp+58h+arg_0]
0x18001b9ea  mov     [rsp+58h+arg_8], eax
0x18001b9ee  mov     rax, [r14]
0x18001b9f1  lea     rcx, dword_180041564
0x18001b9f8  mov     [rsp+58h+var_38], rcx
0x18001b9fd  mov     r9d, 1
0x18001ba03  mov     r8, rdi
0x18001ba06  lea     rdx, [rsp+58h+arg_8]
0x18001ba0b  mov     rcx, r14
0x18001ba0e  mov     rax, [rax+38h]
0x18001ba12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba17  mov     ebx, eax
0x18001ba19  mov     [rsp+58h+var_28], eax
0x18001ba1d  test    eax, eax
0x18001ba1f  jns     short loc_18001BA65
0x18001ba21  lea     rax, WPP_GLOBAL_Control
0x18001ba28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba2f  cmp     rcx, rax
0x18001ba32  jz      loc_18001BAF5
0x18001ba38  cmp     byte ptr [rcx+19h], 2
0x18001ba3c  jb      loc_18001BAF5
0x18001ba42  test    dword ptr [rcx+1Ch], 100h
0x18001ba49  jz      loc_18001BAF5
0x18001ba4f  lea     rcx, aUnableToGetAtt_0; "Unable to get attributes from request w"...
0x18001ba56  call    WppDbgPrint
0x18001ba5b  mov     edx, 0Ch
0x18001ba60  jmp     loc_18001B941
0x18001ba65  mov     edx, [rsp+58h+arg_8]
0x18001ba69  test    edx, edx
0x18001ba6b  jz      loc_18001BAF5
0x18001ba71  mov     rax, [r14]
0x18001ba74  mov     r8, rdi
0x18001ba77  mov     rcx, r14
0x18001ba7a  mov     rax, [rax+20h]
0x18001ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba83  mov     ebx, eax
0x18001ba85  mov     [rsp+58h+var_28], eax
0x18001ba89  test    eax, eax
0x18001ba8b  jns     short loc_18001BAC5
0x18001ba8d  lea     rax, WPP_GLOBAL_Control
0x18001ba94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba9b  cmp     rcx, rax
0x18001ba9e  jz      short loc_18001BAF5
0x18001baa0  cmp     byte ptr [rcx+19h], 2
0x18001baa4  jb      short loc_18001BAF5
0x18001baa6  test    dword ptr [rcx+1Ch], 100h
0x18001baad  jz      short loc_18001BAF5
0x18001baaf  lea     rcx, aUnableToRemove_1; "Unable to remove attributes from reques"...
0x18001bab6  call    WppDbgPrint
0x18001babb  mov     edx, 0Dh
0x18001bac0  jmp     loc_18001B941
0x18001bac5  xor     esi, esi
0x18001bac7  mov     [rsp+58h+var_24], esi
0x18001bacb  cmp     esi, [rsp+58h+arg_8]
0x18001bacf  jnb     short loc_18001BAF5
0x18001bad1  mov     r8d, esi
0x18001bad4  add     r8, r8
0x18001bad7  mov     r8, [rdi+r8*8+8]; struct _IASATTRIBUTE *
0x18001badc  mov     rdx, r14; struct IAttributesRaw *
0x18001badf  mov     rcx, r15; this
0x18001bae2  call    ?EncryptTunnelPassword@CTunnelPassword@@CAJPEAVCPacketRadius@@PEAUIAttributesRaw@@PEAU_IASATTRIBUTE@@@Z; CTunnelPassword::EncryptTunnelPassword(CPacketRadius *,IAttributesRaw *,_IASATTRIBUTE *)
0x18001bae7  mov     ebx, eax
0x18001bae9  mov     [rsp+58h+var_28], eax
0x18001baed  test    eax, eax
0x18001baef  js      short loc_18001BAF5
0x18001baf1  inc     esi
0x18001baf3  jmp     short loc_18001BAC7
0x18001baf5  xor     esi, esi
0x18001baf7  cmp     [rsp+58h+arg_8], esi
0x18001bafb  jbe     short loc_18001BB14
0x18001bafd  mov     ecx, esi
0x18001baff  add     rcx, rcx
0x18001bb02  mov     rcx, [rdi+rcx*8+8]; pv
0x18001bb07  call    IASAttributeRelease
0x18001bb0c  inc     esi
0x18001bb0e  cmp     esi, [rsp+58h+arg_8]
0x18001bb12  jb      short loc_18001BAFD
0x18001bb14  test    rdi, rdi
0x18001bb17  jz      short loc_18001BB22
0x18001bb19  mov     rcx, rdi; pv
0x18001bb1c  call    cs:__imp_CoTaskMemFree
0x18001bb22  mov     eax, ebx
0x18001bb24  mov     rbx, [rsp+58h+arg_10]
0x18001bb29  mov     rsi, [rsp+58h+arg_18]
0x18001bb2e  add     rsp, 40h
0x18001bb32  pop     r15
0x18001bb34  pop     r14
0x18001bb36  pop     rdi
0x18001bb37  retn
0x18002f13e  push    rbx
0x18002f140  push    rbp
0x18002f141  sub     rsp, 38h
0x18002f145  mov     rbp, rdx
0x18002f148  xor     ebx, ebx
0x18002f14a  cmp     [rbp+68h], ebx
0x18002f14d  jbe     short loc_18002F16A
0x18002f14f  mov     eax, ebx
0x18002f151  shl     rax, 4
0x18002f155  mov     rcx, [rbp+38h]
0x18002f159  mov     rcx, [rax+rcx+8]; pv
0x18002f15e  call    IASAttributeRelease
0x18002f163  inc     ebx
0x18002f165  cmp     ebx, [rbp+68h]
0x18002f168  jb      short loc_18002F14F
0x18002f16a  mov     rcx, [rbp+38h]; pv
0x18002f16e  test    rcx, rcx
0x18002f171  jz      short loc_18002F17A
0x18002f173  call    cs:__imp_CoTaskMemFree
0x18002f179  nop
0x18002f17a  add     rsp, 38h
0x18002f17e  pop     rbp
0x18002f17f  pop     rbx
0x18002f180  retn
```
