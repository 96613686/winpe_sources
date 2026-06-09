# GetConfiguredInfo

- ea: `0x180010f00`
- end: `0x180011229`
- name: `GetConfiguredInfo`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ff7c`
- `0x1800139cc`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000bdd0`
- `0x18000be68`
- `0x180010f00`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall GetConfiguredInfo(__int64 a1, int a2, __int64 a3, _DWORD *a4)
{
  unsigned int v7; // esi
  _DWORD *v8; // r12
  _DWORD *v9; // r13
  _DWORD *PointerToCPCB; // rax
  _DWORD *v11; // r10
  _DWORD *v12; // rbx
  char *v13; // r9
  __int64 v14; // r8
  int v15; // eax
  unsigned int v16; // ebp
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // r9d
  const wchar_t *v21; // rdx
  __int64 result; // rax
  char pszDest[32]; // [rsp+30h] [rbp-868h] BYREF
  int v25; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v26[2044]; // [rsp+54h] [rbp-844h] BYREF

  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  *(_DWORD *)a3 = 0;
  v7 = 1;
  v8 = (_DWORD *)(a3 + 4);
  *(_DWORD *)(a3 + 60) = 720;
  v9 = (_DWORD *)(a3 + 136);
  *(_DWORD *)(a3 + 4) = 720;
  *(_DWORD *)(a3 + 136) = 720;
  while ( 1 )
  {
    if ( v7 >= (unsigned int)PppConfigInfo )
    {
      if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
        StringCchCopyA(pszDest, 0x11u, (STRSAFE_LPCSTR)(*(_QWORD *)(a1 + 8) + 1284LL));
      *a4 = 1;
      return 0;
    }
    PointerToCPCB = (_DWORD *)GetPointerToCPCB(a1, v7);
    v12 = PointerToCPCB;
    if ( !PointerToCPCB[11] )
    {
      v20 = PointerToCPCB[10];
      if ( v20 )
      {
        switch ( *((_DWORD *)CpTable + 44 * v7) )
        {
          case 0x8021:
            *v8 = v20;
            break;
          case 0x8057:
            *v11 = v20;
            break;
          case 0x80FD:
            *v9 = v20;
            break;
        }
      }
      goto LABEL_35;
    }
    if ( PointerToCPCB[14] == 1 )
      return 0;
    v13 = (char *)CpTable;
    v14 = 176LL * v7;
    if ( *(_DWORD *)((char *)CpTable + v14) == 32801 )
      break;
    if ( *(_DWORD *)((char *)CpTable + v14) == 32855 )
    {
      v18 = PointerToCPCB[10];
      *v11 = v18;
      if ( !v18 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))&v13[v14 + 136])(*((_QWORD *)v12 + 2), v11);
        if ( v16 )
        {
          if ( (byte_18004DF34 & 1) == 0 )
            goto LABEL_40;
          v21 = L"IPv6CP GetNegotiatedInfo returned %d";
          goto LABEL_38;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL) = *(_QWORD *)(a3 + 72);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 144LL) = *(_QWORD *)(a3 + 80);
      }
    }
    else if ( *(_DWORD *)((char *)CpTable + v14) == 33021 )
    {
      v15 = PointerToCPCB[10];
      *v9 = v15;
      if ( !v15 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))&v13[v14 + 136])(*((_QWORD *)v12 + 2), a3 + 136);
        if ( v16 )
          goto LABEL_40;
        v17 = (unsigned __int16)*(_DWORD *)(a1 + 60);
        if ( v17 != 9 && v17 != 14 )
        {
          switch ( *(_DWORD *)(a3 + 144) & 0xF0 )
          {
            case 16:
            case 32:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x800u;
              break;
            case 64:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x2000u;
              break;
            case 128:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x1000u;
              break;
          }
        }
      }
    }
LABEL_35:
    ++v7;
  }
  v19 = PointerToCPCB[10];
  *v8 = v19;
  if ( v19 )
    goto LABEL_35;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))&v13[v14 + 136])(*((_QWORD *)v12 + 2), a3 + 4);
  if ( !v16 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL) = *(_DWORD *)(a3 + 36);
    if ( *(_DWORD *)(a3 + 8) && *(_DWORD *)(a3 + 12) != v16 )
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x400u;
    goto LABEL_35;
  }
  if ( (byte_18004DF34 & 1) == 0 )
    goto LABEL_40;
  v21 = L"IPCP GetNegotiatedInfo returned %d";
LABEL_38:
  LOWORD(v25) = 0;
  FormatRRASErrorString((wchar_t *)&v25, v21, v16);
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
      (const wchar_t *)&v25);
LABEL_40:
  v12[10] = v16;
  v12[14] = 1;
  FsmClose(a1, v7);
  result = 0;
  if ( v7 == a2 )
    return v16;
  return result;
}

```

## disassembly

```asm
0x180010f00  mov     [rsp+arg_8], rbx
0x180010f05  push    rbp
0x180010f06  push    rsi
0x180010f07  push    rdi
0x180010f08  push    r12
0x180010f0a  push    r13
0x180010f0c  push    r14
0x180010f0e  push    r15
0x180010f10  sub     rsp, 860h
0x180010f17  mov     rax, cs:__security_cookie
0x180010f1e  xor     rax, rsp
0x180010f21  mov     [rsp+898h+var_48], rax
0x180010f29  mov     r14, r8
0x180010f2c  mov     [rsp+898h+var_870], r9
0x180010f31  mov     r15d, edx
0x180010f34  mov     rdi, rcx
0x180010f37  xor     eax, eax
0x180010f39  lea     rcx, [rsp+898h+var_844]; void *
0x180010f3e  xor     edx, edx; Val
0x180010f40  mov     [rsp+898h+var_848], eax
0x180010f44  mov     r8d, 7FCh; Size
0x180010f4a  call    memset_0
0x180010f4f  mov     eax, 2D0h
0x180010f54  mov     dword ptr [r14], 0
0x180010f5b  lea     r10, [r14+3Ch]
0x180010f5f  mov     esi, 1
0x180010f64  lea     r12, [r14+4]
0x180010f68  mov     [r10], eax
0x180010f6b  lea     r13, [r14+88h]
0x180010f72  mov     [r12], eax
0x180010f76  mov     [r13+0], eax
0x180010f7a  cmp     esi, dword ptr cs:PppConfigInfo
0x180010f80  jnb     loc_1800111D0
0x180010f86  mov     edx, esi
0x180010f88  mov     rcx, rdi
0x180010f8b  call    GetPointerToCPCB
0x180010f90  mov     rbx, rax
0x180010f93  cmp     dword ptr [rax+2Ch], 0
0x180010f97  jz      loc_180011110
0x180010f9d  cmp     dword ptr [rax+38h], 1
0x180010fa1  jz      loc_1800111FB
0x180010fa7  mov     r9, cs:CpTable
0x180010fae  mov     ecx, esi
0x180010fb0  imul    r8, rcx, 0B0h
0x180010fb7  mov     eax, [r8+r9]
0x180010fbb  sub     eax, 8021h
0x180010fc0  jz      loc_1800110BD
0x180010fc6  sub     eax, 36h ; '6'
0x180010fc9  jz      loc_180011071
0x180010fcf  cmp     eax, 0A6h
0x180010fd4  jnz     loc_180011154
0x180010fda  mov     eax, [rbx+28h]
0x180010fdd  mov     [r13+0], eax
0x180010fe1  test    eax, eax
0x180010fe3  jnz     loc_180011154
0x180010fe9  mov     rcx, [rbx+10h]
0x180010fed  mov     rdx, r13
0x180010ff0  mov     rax, [r8+r9+88h]
0x180010ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ffd  mov     ebp, eax
0x180010fff  test    eax, eax
0x180011001  jnz     loc_1800111A0
0x180011007  mov     eax, [rdi+3Ch]
0x18001100a  movzx   eax, ax
0x18001100d  cmp     eax, 9
0x180011010  jz      loc_18001110A
0x180011016  cmp     eax, 0Eh
0x180011019  jz      loc_18001110A
0x18001101f  mov     eax, [r14+90h]
0x180011026  and     eax, 0F0h
0x18001102b  sub     eax, 10h
0x18001102e  jz      short loc_180011063
0x180011030  sub     eax, 10h
0x180011033  jz      short loc_180011063
0x180011035  sub     eax, 20h ; ' '
0x180011038  jz      short loc_180011055
0x18001103a  lea     r10, [r14+3Ch]
0x18001103e  cmp     eax, 40h ; '@'
0x180011041  jnz     loc_180011154
0x180011047  mov     rax, [rdi+8]
0x18001104b  bts     dword ptr [rax+34h], 0Ch
0x180011050  jmp     loc_180011154
0x180011055  mov     rax, [rdi+8]
0x180011059  bts     dword ptr [rax+34h], 0Dh
0x18001105e  jmp     loc_18001110A
0x180011063  mov     rax, [rdi+8]
0x180011067  bts     dword ptr [rax+34h], 0Bh
0x18001106c  jmp     loc_18001110A
0x180011071  mov     eax, [rbx+28h]
0x180011074  mov     [r10], eax
0x180011077  test    eax, eax
0x180011079  jnz     loc_180011154
0x18001107f  mov     rcx, [rbx+10h]
0x180011083  mov     rdx, r10
0x180011086  mov     rax, [r8+r9+88h]
0x18001108e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011093  mov     ebp, eax
0x180011095  test    eax, eax
0x180011097  jnz     loc_18001115B
0x18001109d  mov     rcx, [rdi+8]
0x1800110a1  mov     rax, [r14+48h]
0x1800110a5  mov     [rcx+88h], rax
0x1800110ac  mov     rcx, [rdi+8]
0x1800110b0  mov     rax, [r14+50h]
0x1800110b4  mov     [rcx+90h], rax
0x1800110bb  jmp     short loc_18001110A
0x1800110bd  mov     eax, [rbx+28h]
0x1800110c0  mov     [r12], eax
0x1800110c4  test    eax, eax
0x1800110c6  jnz     loc_180011154
0x1800110cc  mov     rcx, [rbx+10h]
0x1800110d0  mov     rdx, r12
0x1800110d3  mov     rax, [r8+r9+88h]
0x1800110db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e0  mov     ebp, eax
0x1800110e2  test    eax, eax
0x1800110e4  jnz     loc_1800111BE
0x1800110ea  mov     rcx, [rdi+8]
0x1800110ee  mov     eax, [r14+24h]
0x1800110f2  mov     [rcx+78h], eax
0x1800110f5  cmp     [r14+8], ebp
0x1800110f9  jz      short loc_18001110A
0x1800110fb  cmp     [r14+0Ch], ebp
0x1800110ff  jz      short loc_18001110A
0x180011101  mov     rax, [rdi+8]
0x180011105  bts     dword ptr [rax+34h], 0Ah
0x18001110a  lea     r10, [r14+3Ch]
0x18001110e  jmp     short loc_180011154
0x180011110  mov     r9d, [rax+28h]
0x180011114  test    r9d, r9d
0x180011117  jz      short loc_180011154
0x180011119  mov     rcx, cs:CpTable
0x180011120  mov     eax, esi
0x180011122  imul    rdx, rax, 0B0h
0x180011129  mov     r8d, [rdx+rcx]
0x18001112d  sub     r8d, 8021h
0x180011134  jz      short loc_180011150
0x180011136  sub     r8d, 36h ; '6'
0x18001113a  jz      short loc_18001114B
0x18001113c  cmp     r8d, 0A6h
0x180011143  jnz     short loc_180011154
0x180011145  mov     [r13+0], r9d
0x180011149  jmp     short loc_180011154
0x18001114b  mov     [r10], r9d
0x18001114e  jmp     short loc_180011154
0x180011150  mov     [r12], r9d
0x180011154  inc     esi
0x180011156  jmp     loc_180010F7A
0x18001115b  test    cs:byte_18004DF34, 1
0x180011162  jz      short loc_1800111A0
0x180011164  lea     rdx, aIpv6cpGetnegot; "IPv6CP GetNegotiatedInfo returned %d"
0x18001116b  xor     eax, eax
0x18001116d  lea     rcx, [rsp+898h+var_848]
0x180011172  mov     r8d, ebp
0x180011175  mov     word ptr [rsp+898h+var_848], ax
0x18001117a  call    FormatRRASErrorString
0x18001117f  test    cs:byte_18004DF34, 1
0x180011186  jz      short loc_1800111A0
0x180011188  lea     r8, [rsp+898h+var_848]
0x18001118d  lea     rdx, RasPppTraceInfo
0x180011194  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001119b  call    McTemplateU0z_EventWriteTransfer
0x1800111a0  mov     edx, esi
0x1800111a2  mov     [rbx+28h], ebp
0x1800111a5  mov     rcx, rdi
0x1800111a8  mov     dword ptr [rbx+38h], 1
0x1800111af  call    FsmClose
0x1800111b4  xor     eax, eax
0x1800111b6  cmp     esi, r15d
0x1800111b9  cmovz   eax, ebp
0x1800111bc  jmp     short loc_1800111FD
0x1800111be  test    cs:byte_18004DF34, 1
0x1800111c5  jz      short loc_1800111A0
0x1800111c7  lea     rdx, aIpcpGetnegotia; "IPCP GetNegotiatedInfo returned %d"
0x1800111ce  jmp     short loc_18001116B
0x1800111d0  test    byte ptr [rdi+38h], 4
0x1800111d4  jz      short loc_1800111F0
0x1800111d6  mov     r8, [rdi+8]
0x1800111da  lea     rcx, [rsp+898h+pszDest]; pszDest
0x1800111df  add     r8, 504h; pszSrc
0x1800111e6  mov     edx, 11h; cchDest
0x1800111eb  call    StringCchCopyA
0x1800111f0  mov     rax, [rsp+898h+var_870]
0x1800111f5  mov     dword ptr [rax], 1
0x1800111fb  xor     eax, eax
0x1800111fd  mov     rcx, [rsp+898h+var_48]
0x180011205  xor     rcx, rsp; StackCookie
0x180011208  call    __security_check_cookie
0x18001120d  mov     rbx, [rsp+898h+arg_8]
0x180011215  add     rsp, 860h
0x18001121c  pop     r15
0x18001121e  pop     r14
0x180011220  pop     r13
0x180011222  pop     r12
0x180011224  pop     rdi
0x180011225  pop     rsi
0x180011226  pop     rbp
0x180011227  retn
```
