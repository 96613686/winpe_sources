# LipsStateTunnelFilterDeleteCb

- ea: `0x180049b30`
- end: `0x180049caf`
- name: `LipsStateTunnelFilterDeleteCb`
- size: `383`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180047f60`
- `0x180048988`
- `0x180049b30`

## string_xrefs

- `0x180049c92`: `LipsStateTunnelFilterDeleteCb`

## pseudocode

```c
__int64 __fastcall LipsStateTunnelFilterDeleteCb(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 *v2; // rdi
  __int64 v3; // rax
  GUID *v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx

  v1 = 0;
  v2 = (__int64 *)(a1 + 328);
  if ( a1 != -328 )
  {
    v3 = *v2;
    if ( *v2 )
    {
      v4 = (GUID *)(v3 + 4);
      if ( *(_DWORD *)v3 )
      {
        v1 = LipsBfeTunnelDelete((GUID *)(v3 + 4));
        if ( v1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v1);
          }
          return (unsigned int)LipsReportError(v1, (int)"LipsStateTunnelFilterDeleteCb");
        }
      }
      else
      {
        v5 = *(_QWORD *)&GUID_NULL.Data1;
        v6 = *(_QWORD *)GUID_NULL.Data4;
        v7 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&v4->Data1;
        if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&v4->Data1 )
          v7 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)v4->Data4;
        if ( v7 )
        {
          v1 = LipsBfeFilterDelete(v4);
          *(_OWORD *)(*v2 + 4) = 0;
          v6 = *(_QWORD *)GUID_NULL.Data4;
          v5 = *(_QWORD *)&GUID_NULL.Data1;
        }
        v8 = *v2;
        v9 = v5 - *(_QWORD *)(*v2 + 20);
        if ( v5 == *(_QWORD *)(*v2 + 20) )
          v9 = v6 - *(_QWORD *)(v8 + 28);
        if ( v9 )
        {
          LipsBfeFilterDelete((GUID *)(v8 + 20));
          *(_OWORD *)(*v2 + 20) = 0;
          v6 = *(_QWORD *)GUID_NULL.Data4;
          v5 = *(_QWORD *)&GUID_NULL.Data1;
        }
        v10 = *v2;
        v11 = v5 - *(_QWORD *)(*v2 + 36);
        if ( v5 == *(_QWORD *)(*v2 + 36) )
          v11 = v6 - *(_QWORD *)(v10 + 44);
        if ( v11 )
        {
          LipsBfeFilterDelete((GUID *)(v10 + 36));
          *(_OWORD *)(*v2 + 36) = 0;
          v6 = *(_QWORD *)GUID_NULL.Data4;
          v5 = *(_QWORD *)&GUID_NULL.Data1;
        }
        v12 = *v2;
        v13 = v5 - *(_QWORD *)(*v2 + 52);
        if ( !v13 )
          v13 = v6 - *(_QWORD *)(v12 + 60);
        if ( v13 )
        {
          LipsBfeFilterDelete((GUID *)(v12 + 52));
          *(_OWORD *)(*v2 + 52) = 0;
        }
        if ( v1 )
          return (unsigned int)LipsReportError(v1, (int)"LipsStateTunnelFilterDeleteCb");
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180049b30  mov     [rsp+arg_0], rbx
0x180049b35  push    rdi
0x180049b36  sub     rsp, 20h
0x180049b3a  xor     ebx, ebx
0x180049b3c  lea     rdi, [rcx+148h]
0x180049b43  test    rdi, rdi
0x180049b46  jz      loc_180049CA2
0x180049b4c  mov     rax, [rdi]
0x180049b4f  test    rax, rax
0x180049b52  jz      loc_180049CA2
0x180049b58  lea     r8, [rax+4]
0x180049b5c  cmp     [rax], ebx
0x180049b5e  jz      short loc_180049BB0
0x180049b60  mov     rcx, r8; key
0x180049b63  call    LipsBfeTunnelDelete
0x180049b68  mov     ebx, eax
0x180049b6a  test    eax, eax
0x180049b6c  jz      loc_180049CA2
0x180049b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b79  lea     rax, WPP_GLOBAL_Control
0x180049b80  cmp     rcx, rax
0x180049b83  jz      loc_180049C92
0x180049b89  test    byte ptr [rcx+1Ch], 10h
0x180049b8d  jz      loc_180049C92
0x180049b93  mov     rcx, [rcx+10h]
0x180049b97  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049b9e  mov     edx, 0Fh
0x180049ba3  mov     r9d, ebx
0x180049ba6  call    WPP_SF_d
0x180049bab  jmp     loc_180049C92
0x180049bb0  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180049bb7  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180049bbe  mov     rax, rcx
0x180049bc1  sub     rax, [r8]
0x180049bc4  jnz     short loc_180049BCD
0x180049bc6  mov     rax, rdx
0x180049bc9  sub     rax, [r8+8]
0x180049bcd  test    rax, rax
0x180049bd0  jz      short loc_180049BF4
0x180049bd2  mov     rcx, r8; key
0x180049bd5  call    LipsBfeFilterDelete
0x180049bda  mov     ebx, eax
0x180049bdc  xorps   xmm0, xmm0
0x180049bdf  mov     rax, [rdi]
0x180049be2  movups  xmmword ptr [rax+4], xmm0
0x180049be6  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180049bed  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180049bf4  mov     r8, [rdi]
0x180049bf7  mov     rax, rcx
0x180049bfa  sub     rax, [r8+14h]
0x180049bfe  jnz     short loc_180049C07
0x180049c00  mov     rax, rdx
0x180049c03  sub     rax, [r8+1Ch]
0x180049c07  test    rax, rax
0x180049c0a  jz      short loc_180049C2D
0x180049c0c  lea     rcx, [r8+14h]; key
0x180049c10  call    LipsBfeFilterDelete
0x180049c15  mov     rax, [rdi]
0x180049c18  xorps   xmm0, xmm0
0x180049c1b  movups  xmmword ptr [rax+14h], xmm0
0x180049c1f  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180049c26  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180049c2d  mov     r8, [rdi]
0x180049c30  mov     rax, rcx
0x180049c33  sub     rax, [r8+24h]
0x180049c37  jnz     short loc_180049C40
0x180049c39  mov     rax, rdx
0x180049c3c  sub     rax, [r8+2Ch]
0x180049c40  test    rax, rax
0x180049c43  jz      short loc_180049C66
0x180049c45  lea     rcx, [r8+24h]; key
0x180049c49  call    LipsBfeFilterDelete
0x180049c4e  mov     rax, [rdi]
0x180049c51  xorps   xmm0, xmm0
0x180049c54  movups  xmmword ptr [rax+24h], xmm0
0x180049c58  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180049c5f  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180049c66  mov     rax, [rdi]
0x180049c69  sub     rcx, [rax+34h]
0x180049c6d  jnz     short loc_180049C76
0x180049c6f  mov     rcx, rdx
0x180049c72  sub     rcx, [rax+3Ch]
0x180049c76  test    rcx, rcx
0x180049c79  jz      short loc_180049C8E
0x180049c7b  lea     rcx, [rax+34h]; key
0x180049c7f  call    LipsBfeFilterDelete
0x180049c84  mov     rax, [rdi]
0x180049c87  xorps   xmm0, xmm0
0x180049c8a  movups  xmmword ptr [rax+34h], xmm0
0x180049c8e  test    ebx, ebx
0x180049c90  jz      short loc_180049CA2
0x180049c92  lea     rdx, aLipsstatetunne_5; "LipsStateTunnelFilterDeleteCb"
0x180049c99  mov     ecx, ebx
0x180049c9b  call    LipsReportError
0x180049ca0  mov     ebx, eax
0x180049ca2  mov     eax, ebx
0x180049ca4  mov     rbx, [rsp+28h+arg_0]
0x180049ca9  add     rsp, 20h
0x180049cad  pop     rdi
0x180049cae  retn
```
