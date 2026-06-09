# CopyExtraBuffers(_SecBufferInfoArray *,_SecBufferDesc *)

- ea: `0x180004b38`
- end: `0x180004c6b`
- name: `?CopyExtraBuffers@@YAJPEAU_SecBufferInfoArray@@PEAU_SecBufferDesc@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct _SecBufferInfoArray *, struct _SecBufferDesc *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002a84`

## callees

- `0x180004b38`
- `0x180007ba8`
- `0x18000b298`
- `0x18000b350`

## pseudocode

```c
__int64 __fastcall CopyExtraBuffers(struct _SecBufferInfoArray *a1, struct _SecBufferDesc *a2)
{
  unsigned int v4; // r8d
  __int64 v6; // rsi
  unsigned int v7; // ecx
  __int64 v8; // r8

  if ( a1 )
  {
    if ( !a2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids);
      return 261;
    }
    v4 = *((_DWORD *)a1 + 1);
    if ( v4 > a2->cBuffers )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids);
      return 261;
    }
    v6 = 0;
    if ( v4 )
    {
      do
      {
        v7 = *(_DWORD *)(8 * v6 + *((_QWORD *)a1 + 1) + 4);
        if ( v7 - 4 <= 1 )
        {
          v8 = (unsigned int)v6;
          a2->pBuffers[v8].BufferType = v7;
          a2->pBuffers[v8].cbBuffer = *(_DWORD *)(8 * v6 + *((_QWORD *)a1 + 1));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
            WPP_SF_LLqL(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              a2->pBuffers,
              v8 * 2,
              (unsigned int)v6,
              a2->pBuffers[(unsigned int)v6].BufferType,
              a2->pBuffers[(unsigned int)v6].pvBuffer,
              a2->pBuffers[(unsigned int)v6].cbBuffer);
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *((_DWORD *)a1 + 1) );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004b38  push    rbx
0x180004b3a  push    rbp
0x180004b3b  push    rsi
0x180004b3c  push    rdi
0x180004b3d  sub     rsp, 48h
0x180004b41  mov     rbp, rdx
0x180004b44  mov     rdi, rcx
0x180004b47  test    rcx, rcx
0x180004b4a  jz      loc_180004C5F
0x180004b50  test    rdx, rdx
0x180004b53  jnz     short loc_180004B84
0x180004b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b5c  lea     rbx, WPP_GLOBAL_Control
0x180004b63  cmp     rcx, rbx
0x180004b66  jz      short loc_180004BC8
0x180004b68  mov     eax, [rcx+2Ch]
0x180004b6b  test    al, 1
0x180004b6d  jz      short loc_180004BC8
0x180004b6f  mov     rcx, [rcx+18h]
0x180004b73  lea     edx, [rbp+0Ah]
0x180004b76  lea     r8, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids
0x180004b7d  call    WPP_SF_
0x180004b82  jmp     short loc_180004BC8
0x180004b84  mov     r9d, [rdx+4]
0x180004b88  mov     r8d, [rcx+4]
0x180004b8c  cmp     r8d, r9d
0x180004b8f  jbe     short loc_180004BD2
0x180004b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b98  lea     rbx, WPP_GLOBAL_Control
0x180004b9f  cmp     rcx, rbx
0x180004ba2  jz      short loc_180004BC8
0x180004ba4  mov     eax, [rcx+2Ch]
0x180004ba7  test    al, 1
0x180004ba9  jz      short loc_180004BC8
0x180004bab  mov     rcx, [rcx+18h]
0x180004baf  mov     edx, 0Bh
0x180004bb4  mov     [rsp+68h+var_48], r9d
0x180004bb9  mov     r9d, r8d
0x180004bbc  lea     r8, WPP_c36fb4c2aaf6301e6032cbac527c9a1d_Traceguids
0x180004bc3  call    WPP_SF_LL
0x180004bc8  mov     eax, 105h
0x180004bcd  jmp     loc_180004C61
0x180004bd2  xor     esi, esi
0x180004bd4  test    r8d, r8d
0x180004bd7  jz      loc_180004C5F
0x180004bdd  lea     rbx, WPP_GLOBAL_Control
0x180004be4  mov     rax, [rdi+8]
0x180004be8  lea     rdx, ds:0[rsi*8]
0x180004bf0  mov     r8d, esi
0x180004bf3  mov     ecx, [rdx+rax+4]
0x180004bf7  lea     eax, [rcx-4]
0x180004bfa  cmp     eax, 1
0x180004bfd  ja      short loc_180004C58
0x180004bff  mov     rax, [rbp+8]
0x180004c03  add     r8, r8
0x180004c06  mov     [rax+r8*8+4], ecx
0x180004c0b  mov     rax, [rdi+8]
0x180004c0f  mov     rcx, [rbp+8]
0x180004c13  mov     eax, [rdx+rax]
0x180004c16  mov     [rcx+r8*8], eax
0x180004c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c21  cmp     rcx, rbx
0x180004c24  jz      short loc_180004C58
0x180004c26  mov     eax, [rcx+2Ch]
0x180004c29  test    al, 8
0x180004c2b  jz      short loc_180004C58
0x180004c2d  mov     rdx, [rbp+8]
0x180004c31  mov     r9d, esi
0x180004c34  mov     rcx, [rcx+18h]
0x180004c38  mov     eax, [rdx+r8*8]
0x180004c3c  mov     [rsp+68h+var_38], eax
0x180004c40  mov     rax, [rdx+r8*8+8]
0x180004c45  mov     [rsp+68h+var_40], rax
0x180004c4a  mov     eax, [rdx+r8*8+4]
0x180004c4f  mov     [rsp+68h+var_48], eax
0x180004c53  call    WPP_SF_LLqL
0x180004c58  inc     esi
0x180004c5a  cmp     esi, [rdi+4]
0x180004c5d  jb      short loc_180004BE4
0x180004c5f  xor     eax, eax
0x180004c61  add     rsp, 48h
0x180004c65  pop     rdi
0x180004c66  pop     rsi
0x180004c67  pop     rbp
0x180004c68  pop     rbx
0x180004c69  retn
```
