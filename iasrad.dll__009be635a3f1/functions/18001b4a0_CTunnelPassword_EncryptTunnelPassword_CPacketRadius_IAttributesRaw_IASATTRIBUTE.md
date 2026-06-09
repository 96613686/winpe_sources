# CTunnelPassword::EncryptTunnelPassword(CPacketRadius *,IAttributesRaw *,_IASATTRIBUTE *)

- ea: `0x18001b4a0`
- end: `0x18001b74f`
- name: `?EncryptTunnelPassword@CTunnelPassword@@CAJPEAVCPacketRadius@@PEAUIAttributesRaw@@PEAU_IASATTRIBUTE@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct CPacketRadius *this, struct IAttributesRaw *, struct _IASATTRIBUTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b898`

## callees

- `0x180002106`
- `0x1800094e4`
- `0x18001450c`
- `0x18001b4a0`
- `0x18001d31c`
- `0x18002ada0`
- `0x18002af04`
- `0x18002e202`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b60f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b60f`

## string_xrefs

- `0x18001b70e`: `Arithmetic overflow when computing the attr length of tunnel password`

## pseudocode

```c
__int64 __fastcall CTunnelPassword::EncryptTunnelPassword(
        struct CPacketRadius *this,
        struct IAttributesRaw *a2,
        struct _IASATTRIBUTE *a3)
{
  unsigned int v3; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // edi
  _DWORD *v11; // rbx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rbp
  __int64 v14; // rax
  unsigned int v15; // edi
  _QWORD v16[9]; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF

  v3 = *((_DWORD *)a3 + 6);
  if ( v3 < 4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      return 2147942487LL;
    }
    WppDbgPrint("Tunnel password attribute is invalid - it has less than 4 bytes of data");
    v7 = 14;
LABEL_12:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
    return 2147942487LL;
  }
  v8 = (v3 + 12) & 0xFFFFFFF0;
  if ( v8 < 0x10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Arithmetic overflow when computing the attr length of tunnel password");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
    }
    return 534;
  }
  else
  {
    v9 = v8 + 3;
    if ( v8 + 3 > 0xFD )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        return 2147942487LL;
      }
      WppDbgPrint("Tunnel password attribute is invalid - it has more than 253 bytes of data");
      v7 = 16;
      goto LABEL_12;
    }
    pv = 0;
    if ( (unsigned int)IASAttributeAlloc(1, &pv) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Not enough memory to allocate for the tunnel password attribute");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
      }
      return 2147942414LL;
    }
    else
    {
      v11 = pv;
      *((_DWORD *)pv + 2) = 69;
      v11[1] = *((_DWORD *)a3 + 1);
      v11[4] = 6;
      v11[6] = v9;
      v12 = (unsigned __int8 *)CoTaskMemAlloc(v9);
      *((_QWORD *)v11 + 4) = v12;
      v13 = v12;
      if ( v12 )
      {
        memcpy_0(v12, *((const void **)a3 + 4), *((unsigned int *)a3 + 6));
        memset_0(&v13[*((unsigned int *)a3 + 6)], 0, v9 - *((_DWORD *)a3 + 6));
        CPacketRadius::cryptBuffer(this, 1, 1, v13 + 1, v9 - 1);
        v14 = *(_QWORD *)a2;
        v16[0] = 0;
        v16[1] = v11;
        v15 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, __int64, _QWORD *))(v14 + 24))(a2, 1, v16);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Not enough memory to allocate for the tunnel password attribute value");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids, "NPSRAD");
        }
        v15 = -2147024882;
      }
      IASAttributeRelease(v11);
      return v15;
    }
  }
}

```

## disassembly

```asm
0x18001b4a0  push    rbx
0x18001b4a2  push    rbp
0x18001b4a3  push    rsi
0x18001b4a4  push    rdi
0x18001b4a5  push    r14
0x18001b4a7  push    r15
0x18001b4a9  sub     rsp, 48h
0x18001b4ad  mov     eax, [r8+18h]
0x18001b4b1  mov     rsi, r8
0x18001b4b4  mov     r14, rdx
0x18001b4b7  mov     r15, rcx
0x18001b4ba  cmp     eax, 4
0x18001b4bd  jnb     short loc_18001B4FC
0x18001b4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4c6  lea     rax, WPP_GLOBAL_Control
0x18001b4cd  cmp     rcx, rax
0x18001b4d0  jz      loc_18001B567
0x18001b4d6  cmp     byte ptr [rcx+19h], 2
0x18001b4da  jb      loc_18001B567
0x18001b4e0  test    dword ptr [rcx+1Ch], 100h
0x18001b4e7  jz      short loc_18001B567
0x18001b4e9  lea     rcx, aTunnelPassword_0; "Tunnel password attribute is invalid - "...
0x18001b4f0  call    WppDbgPrint
0x18001b4f5  mov     edx, 0Eh
0x18001b4fa  jmp     short loc_18001B549
0x18001b4fc  add     eax, 0Ch
0x18001b4ff  and     eax, 0FFFFFFF0h
0x18001b502  cmp     eax, 10h
0x18001b505  jb      loc_18001B6EC
0x18001b50b  lea     edi, [rax+3]
0x18001b50e  cmp     edi, 0FDh
0x18001b514  jbe     short loc_18001B571
0x18001b516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b51d  lea     rax, WPP_GLOBAL_Control
0x18001b524  cmp     rcx, rax
0x18001b527  jz      short loc_18001B567
0x18001b529  cmp     byte ptr [rcx+19h], 2
0x18001b52d  jb      short loc_18001B567
0x18001b52f  test    dword ptr [rcx+1Ch], 100h
0x18001b536  jz      short loc_18001B567
0x18001b538  lea     rcx, aTunnelPassword; "Tunnel password attribute is invalid - "...
0x18001b53f  call    WppDbgPrint
0x18001b544  mov     edx, 10h
0x18001b549  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b550  lea     r9, aNpsrad; "NPSRAD"
0x18001b557  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b55e  mov     rcx, [rcx+10h]
0x18001b562  call    WPP_SF_s
0x18001b567  mov     eax, 80070057h
0x18001b56c  jmp     loc_18001B742
0x18001b571  lea     rdx, [rsp+78h+pv]
0x18001b579  mov     [rsp+78h+pv], 0
0x18001b585  mov     ecx, 1
0x18001b58a  call    IASAttributeAlloc
0x18001b58f  test    eax, eax
0x18001b591  jz      short loc_18001B5EE
0x18001b593  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b59a  lea     rax, WPP_GLOBAL_Control
0x18001b5a1  cmp     rcx, rax
0x18001b5a4  jz      short loc_18001B5E4
0x18001b5a6  cmp     byte ptr [rcx+19h], 2
0x18001b5aa  jb      short loc_18001B5E4
0x18001b5ac  test    dword ptr [rcx+1Ch], 100h
0x18001b5b3  jz      short loc_18001B5E4
0x18001b5b5  lea     rcx, aNotEnoughMemor_0; "Not enough memory to allocate for the t"...
0x18001b5bc  call    WppDbgPrint
0x18001b5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5c8  lea     r9, aNpsrad; "NPSRAD"
0x18001b5cf  mov     edx, 11h
0x18001b5d4  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b5db  mov     rcx, [rcx+10h]
0x18001b5df  call    WPP_SF_s
0x18001b5e4  mov     eax, 8007000Eh
0x18001b5e9  jmp     loc_18001B742
0x18001b5ee  mov     rbx, [rsp+78h+pv]
0x18001b5f6  mov     ecx, edi; cb
0x18001b5f8  mov     dword ptr [rbx+8], 45h ; 'E'
0x18001b5ff  mov     eax, [rsi+4]
0x18001b602  mov     [rbx+4], eax
0x18001b605  mov     dword ptr [rbx+10h], 6
0x18001b60c  mov     [rbx+18h], edi
0x18001b60f  call    cs:__imp_CoTaskMemAlloc
0x18001b615  mov     [rbx+20h], rax
0x18001b619  mov     rbp, rax
0x18001b61c  test    rax, rax
0x18001b61f  jz      short loc_18001B68A
0x18001b621  mov     r8d, [rsi+18h]; Size
0x18001b625  mov     rcx, rax; void *
0x18001b628  mov     rdx, [rsi+20h]; Src
0x18001b62c  call    memcpy_0
0x18001b631  mov     ecx, [rsi+18h]
0x18001b634  mov     r8d, edi
0x18001b637  sub     r8d, ecx; Size
0x18001b63a  xor     edx, edx; Val
0x18001b63c  add     rcx, rbp; void *
0x18001b63f  call    memset_0
0x18001b644  mov     edx, 1; int
0x18001b649  lea     eax, [rdi-1]
0x18001b64c  mov     r8d, edx; int
0x18001b64f  mov     [rsp+78h+var_58], eax; unsigned int
0x18001b653  lea     r9, [rbp+1]; unsigned __int8 *
0x18001b657  mov     rcx, r15; this
0x18001b65a  call    ?cryptBuffer@CPacketRadius@@QEBAJHHPEAEK@Z; CPacketRadius::cryptBuffer(int,int,uchar *,ulong)
0x18001b65f  mov     rax, [r14]
0x18001b662  lea     r8, [rsp+78h+var_48]
0x18001b667  mov     edx, 1
0x18001b66c  mov     [rsp+78h+var_48], 0
0x18001b675  mov     rcx, r14
0x18001b678  mov     [rsp+78h+var_40], rbx
0x18001b67d  mov     rax, [rax+18h]
0x18001b681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b686  mov     edi, eax
0x18001b688  jmp     short loc_18001B6E0
0x18001b68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b691  lea     rax, WPP_GLOBAL_Control
0x18001b698  cmp     rcx, rax
0x18001b69b  jz      short loc_18001B6DB
0x18001b69d  cmp     byte ptr [rcx+19h], 2
0x18001b6a1  jb      short loc_18001B6DB
0x18001b6a3  test    dword ptr [rcx+1Ch], 100h
0x18001b6aa  jz      short loc_18001B6DB
0x18001b6ac  lea     rcx, aNotEnoughMemor_1; "Not enough memory to allocate for the t"...
0x18001b6b3  call    WppDbgPrint
0x18001b6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6bf  lea     r9, aNpsrad; "NPSRAD"
0x18001b6c6  mov     edx, 12h
0x18001b6cb  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b6d2  mov     rcx, [rcx+10h]
0x18001b6d6  call    WPP_SF_s
0x18001b6db  mov     edi, 8007000Eh
0x18001b6e0  mov     rcx, rbx; pv
0x18001b6e3  call    IASAttributeRelease
0x18001b6e8  mov     eax, edi
0x18001b6ea  jmp     short loc_18001B742
0x18001b6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6f3  lea     rax, WPP_GLOBAL_Control
0x18001b6fa  cmp     rcx, rax
0x18001b6fd  jz      short loc_18001B73D
0x18001b6ff  cmp     byte ptr [rcx+19h], 2
0x18001b703  jb      short loc_18001B73D
0x18001b705  test    dword ptr [rcx+1Ch], 100h
0x18001b70c  jz      short loc_18001B73D
0x18001b70e  lea     rcx, aArithmeticOver; "Arithmetic overflow when computing the "...
0x18001b715  call    WppDbgPrint
0x18001b71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b721  lea     r9, aNpsrad; "NPSRAD"
0x18001b728  mov     edx, 0Fh
0x18001b72d  lea     r8, WPP_8795a36f9b5d331cba9a21bd0aaf8864_Traceguids
0x18001b734  mov     rcx, [rcx+10h]
0x18001b738  call    WPP_SF_s
0x18001b73d  mov     eax, 216h
0x18001b742  add     rsp, 48h
0x18001b746  pop     r15
0x18001b748  pop     r14
0x18001b74a  pop     rdi
0x18001b74b  pop     rsi
0x18001b74c  pop     rbp
0x18001b74d  pop     rbx
0x18001b74e  retn
```
