# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>)

- ea: `0x18001ae70`
- end: `0x18001b0f4`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `644`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018f90`

## callees

- `0x180018990`
- `0x18001ae70`
- `0x18001b22c`
- `0x18001b27c`
- `0x18001b2a0`

## pseudocode

```c
__int64 *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Extract(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v3; // rdx
  __int64 *v4; // r11
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 **v12; // rcx
  char v13; // cl
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 *v18; // [rsp+38h] [rbp+10h] BYREF

  v18 = a2;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>::operator++(&v18);
  v5 = v4[2];
  if ( *(_BYTE *)(*v4 + 25) )
    goto LABEL_5;
  if ( *(_BYTE *)(v5 + 25) )
  {
    v5 = *v4;
LABEL_5:
    v6 = v4[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    if ( (__int64 *)(*a1)[1] == v4 )
    {
      (*a1)[1] = v5;
    }
    else if ( *(__int64 **)v6 == v4 )
    {
      *(_QWORD *)v6 = v5;
    }
    else
    {
      *(_QWORD *)(v6 + 16) = v5;
    }
    v7 = *a1;
    if ( (__int64 *)**a1 == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
        v8 = v6;
      else
        v8 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Min(
               v5,
               v3,
               v7,
               v6);
      *v7 = v8;
    }
    if ( (__int64 *)(*a1)[2] == v4 )
    {
      if ( *(_BYTE *)(v5 + 25) )
      {
        v9 = v6;
      }
      else
      {
        v10 = *(_QWORD *)(v5 + 16);
        v9 = v5;
        while ( !*(_BYTE *)(v10 + 25) )
        {
          v9 = *(_QWORD *)(v9 + 16);
          v10 = *(_QWORD *)(v9 + 16);
        }
      }
      (*a1)[2] = v9;
    }
    goto LABEL_35;
  }
  v3 = v18;
  v5 = v18[2];
  if ( v18 == v4 )
    goto LABEL_5;
  *(_QWORD *)(*v4 + 8) = v18;
  *v3 = *v4;
  if ( v3 == (__int64 *)v4[2] )
  {
    v6 = (__int64)v3;
  }
  else
  {
    v6 = v3[1];
    if ( !*(_BYTE *)(v5 + 25) )
      *(_QWORD *)(v5 + 8) = v6;
    *(_QWORD *)v6 = v5;
    v3[2] = v4[2];
    *(_QWORD *)(v4[2] + 8) = v3;
  }
  if ( (__int64 *)(*a1)[1] == v4 )
  {
    (*a1)[1] = (__int64)v3;
    v11 = v4 + 1;
  }
  else
  {
    v11 = v4 + 1;
    v12 = (__int64 **)v4[1];
    if ( *v12 == v4 )
      *v12 = v3;
    else
      v12[2] = v3;
  }
  v3[1] = *v11;
  v13 = *((_BYTE *)v3 + 24);
  *((_BYTE *)v3 + 24) = *((_BYTE *)v4 + 24);
  *((_BYTE *)v4 + 24) = v13;
LABEL_35:
  if ( *((_BYTE *)v4 + 24) != 1 )
    goto LABEL_58;
  while ( v5 != (*a1)[1] && *(_BYTE *)(v5 + 24) == 1 )
  {
    v14 = *(_QWORD *)v6;
    if ( v5 == *(_QWORD *)v6 )
    {
      v14 = *(_QWORD *)(v6 + 16);
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(a1);
        v14 = *(_QWORD *)(v6 + 16);
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 || *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) == 1 )
          {
            *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(
              a1,
              v14);
            v14 = *(_QWORD *)(v6 + 16);
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v14 + 16) + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(a1);
          break;
        }
LABEL_52:
        *(_BYTE *)(v14 + 24) = 0;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v14 + 24) )
      {
        *(_BYTE *)(v14 + 24) = 1;
        *(_BYTE *)(v6 + 24) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(
          a1,
          v6);
        v14 = *(_QWORD *)v6;
      }
      if ( !*(_BYTE *)(v14 + 25) )
      {
        v15 = *(_QWORD *)(v14 + 16);
        if ( *(_BYTE *)(v15 + 24) != 1 || *(_BYTE *)(*(_QWORD *)v14 + 24LL) != 1 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v14 + 24LL) == 1 )
          {
            *(_BYTE *)(v15 + 24) = 1;
            *(_BYTE *)(v14 + 24) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(a1);
            v14 = *(_QWORD *)v6;
          }
          *(_BYTE *)(v14 + 24) = *(_BYTE *)(v6 + 24);
          *(_BYTE *)(v6 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)v14 + 24LL) = 1;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(
            a1,
            v6);
          break;
        }
        goto LABEL_52;
      }
    }
    v5 = v6;
    v6 = *(_QWORD *)(v6 + 8);
  }
  *(_BYTE *)(v5 + 24) = 1;
LABEL_58:
  v16 = a1[1];
  if ( v16 )
    a1[1] = (__int64 *)((char *)v16 - 1);
  return v4;
}

```

## disassembly

```asm
0x18001ae70  mov     [rsp+arg_0], rbx
0x18001ae75  mov     [rsp+arg_8], rdx
0x18001ae7a  push    rsi
0x18001ae7b  sub     rsp, 20h
0x18001ae7f  mov     rbx, rcx
0x18001ae82  mov     r11, rdx
0x18001ae85  lea     rcx, [rsp+28h+arg_8]
0x18001ae8a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>::operator++(void)
0x18001ae8f  mov     r9, [r11]
0x18001ae92  xor     esi, esi
0x18001ae94  mov     r10, [r11+10h]
0x18001ae98  cmp     [r9+19h], sil
0x18001ae9c  jnz     short loc_18001AEB7
0x18001ae9e  cmp     [r10+19h], sil
0x18001aea2  jz      short loc_18001AEA9
0x18001aea4  mov     r10, r9
0x18001aea7  jmp     short loc_18001AEB7
0x18001aea9  mov     rdx, [rsp+28h+arg_8]
0x18001aeae  mov     r10, [rdx+10h]
0x18001aeb2  cmp     rdx, r11
0x18001aeb5  jnz     short loc_18001AF35
0x18001aeb7  mov     r9, [r11+8]
0x18001aebb  cmp     [r10+19h], sil
0x18001aebf  jnz     short loc_18001AEC5
0x18001aec1  mov     [r10+8], r9
0x18001aec5  mov     rax, [rbx]
0x18001aec8  cmp     [rax+8], r11
0x18001aecc  jnz     short loc_18001AED4
0x18001aece  mov     [rax+8], r10
0x18001aed2  jmp     short loc_18001AEE2
0x18001aed4  cmp     [r9], r11
0x18001aed7  jnz     short loc_18001AEDE
0x18001aed9  mov     [r9], r10
0x18001aedc  jmp     short loc_18001AEE2
0x18001aede  mov     [r9+10h], r10
0x18001aee2  mov     r8, [rbx]
0x18001aee5  cmp     [r8], r11
0x18001aee8  jnz     short loc_18001AF00
0x18001aeea  cmp     [r10+19h], sil
0x18001aeee  jz      short loc_18001AEF5
0x18001aef0  mov     rax, r9
0x18001aef3  jmp     short loc_18001AEFD
0x18001aef5  mov     rcx, r10
0x18001aef8  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Min(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001aefd  mov     [r8], rax
0x18001af00  mov     rdx, [rbx]
0x18001af03  cmp     [rdx+10h], r11
0x18001af07  jnz     loc_18001AFA8
0x18001af0d  cmp     [r10+19h], sil
0x18001af11  jz      short loc_18001AF18
0x18001af13  mov     rcx, r9
0x18001af16  jmp     short loc_18001AF2F
0x18001af18  mov     rax, [r10+10h]
0x18001af1c  mov     rcx, r10
0x18001af1f  jmp     short loc_18001AF29
0x18001af21  mov     rcx, [rcx+10h]
0x18001af25  mov     rax, [rcx+10h]
0x18001af29  cmp     [rax+19h], sil
0x18001af2d  jz      short loc_18001AF21
0x18001af2f  mov     [rdx+10h], rcx
0x18001af33  jmp     short loc_18001AFA8
0x18001af35  mov     [r9+8], rdx
0x18001af39  mov     rax, [r11]
0x18001af3c  mov     [rdx], rax
0x18001af3f  cmp     rdx, [r11+10h]
0x18001af43  jnz     short loc_18001AF4A
0x18001af45  mov     r9, rdx
0x18001af48  jmp     short loc_18001AF6B
0x18001af4a  mov     r9, [rdx+8]
0x18001af4e  cmp     [r10+19h], sil
0x18001af52  jnz     short loc_18001AF58
0x18001af54  mov     [r10+8], r9
0x18001af58  mov     [r9], r10
0x18001af5b  mov     rax, [r11+10h]
0x18001af5f  mov     [rdx+10h], rax
0x18001af63  mov     rax, [r11+10h]
0x18001af67  mov     [rax+8], rdx
0x18001af6b  mov     rax, [rbx]
0x18001af6e  cmp     [rax+8], r11
0x18001af72  jnz     short loc_18001AF7E
0x18001af74  mov     [rax+8], rdx
0x18001af78  lea     rax, [r11+8]
0x18001af7c  jmp     short loc_18001AF93
0x18001af7e  lea     rax, [r11+8]
0x18001af82  mov     rcx, [rax]
0x18001af85  cmp     [rcx], r11
0x18001af88  jnz     short loc_18001AF8F
0x18001af8a  mov     [rcx], rdx
0x18001af8d  jmp     short loc_18001AF93
0x18001af8f  mov     [rcx+10h], rdx
0x18001af93  mov     rax, [rax]
0x18001af96  mov     [rdx+8], rax
0x18001af9a  mov     al, [r11+18h]
0x18001af9e  mov     cl, [rdx+18h]
0x18001afa1  mov     [rdx+18h], al
0x18001afa4  mov     [r11+18h], cl
0x18001afa8  cmp     byte ptr [r11+18h], 1
0x18001afad  jnz     loc_18001B0D6
0x18001afb3  mov     rax, [rbx]
0x18001afb6  cmp     r10, [rax+8]
0x18001afba  jz      loc_18001B0D1
0x18001afc0  cmp     byte ptr [r10+18h], 1
0x18001afc5  jnz     loc_18001B0D1
0x18001afcb  mov     rdx, [r9]
0x18001afce  cmp     r10, rdx
0x18001afd1  jnz     short loc_18001B052
0x18001afd3  mov     rdx, [r9+10h]
0x18001afd7  cmp     [rdx+18h], sil
0x18001afdb  jnz     short loc_18001AFF4
0x18001afdd  mov     byte ptr [rdx+18h], 1
0x18001afe1  mov     rcx, rbx
0x18001afe4  mov     rdx, r9
0x18001afe7  mov     [r9+18h], sil
0x18001afeb  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001aff0  mov     rdx, [r9+10h]
0x18001aff4  cmp     [rdx+19h], sil
0x18001aff8  jnz     loc_18001B08B
0x18001affe  mov     r8, [rdx]
0x18001b001  cmp     byte ptr [r8+18h], 1
0x18001b006  jnz     short loc_18001B012
0x18001b008  mov     rax, [rdx+10h]
0x18001b00c  cmp     byte ptr [rax+18h], 1
0x18001b010  jz      short loc_18001B087
0x18001b012  mov     rax, [rdx+10h]
0x18001b016  cmp     byte ptr [rax+18h], 1
0x18001b01a  jnz     short loc_18001B031
0x18001b01c  mov     byte ptr [r8+18h], 1
0x18001b021  mov     rcx, rbx
0x18001b024  mov     [rdx+18h], sil
0x18001b028  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001b02d  mov     rdx, [r9+10h]
0x18001b031  mov     al, [r9+18h]
0x18001b035  mov     rcx, rbx
0x18001b038  mov     [rdx+18h], al
0x18001b03b  mov     byte ptr [r9+18h], 1
0x18001b040  mov     rax, [rdx+10h]
0x18001b044  mov     rdx, r9
0x18001b047  mov     byte ptr [rax+18h], 1
0x18001b04b  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001b050  jmp     short loc_18001B0D1
0x18001b052  cmp     [rdx+18h], sil
0x18001b056  jnz     short loc_18001B06E
0x18001b058  mov     byte ptr [rdx+18h], 1
0x18001b05c  mov     rcx, rbx
0x18001b05f  mov     rdx, r9
0x18001b062  mov     [r9+18h], sil
0x18001b066  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001b06b  mov     rdx, [r9]
0x18001b06e  cmp     [rdx+19h], sil
0x18001b072  jnz     short loc_18001B08B
0x18001b074  mov     rcx, [rdx+10h]
0x18001b078  cmp     byte ptr [rcx+18h], 1
0x18001b07c  jnz     short loc_18001B097
0x18001b07e  mov     rax, [rdx]
0x18001b081  cmp     byte ptr [rax+18h], 1
0x18001b085  jnz     short loc_18001B097
0x18001b087  mov     [rdx+18h], sil
0x18001b08b  mov     r10, r9
0x18001b08e  mov     r9, [r9+8]
0x18001b092  jmp     loc_18001AFB3
0x18001b097  mov     rax, [rdx]
0x18001b09a  cmp     byte ptr [rax+18h], 1
0x18001b09e  jnz     short loc_18001B0B3
0x18001b0a0  mov     byte ptr [rcx+18h], 1
0x18001b0a4  mov     rcx, rbx
0x18001b0a7  mov     [rdx+18h], sil
0x18001b0ab  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001b0b0  mov     rdx, [r9]
0x18001b0b3  mov     al, [r9+18h]
0x18001b0b7  mov     rcx, rbx
0x18001b0ba  mov     [rdx+18h], al
0x18001b0bd  mov     byte ptr [r9+18h], 1
0x18001b0c2  mov     rax, [rdx]
0x18001b0c5  mov     rdx, r9
0x18001b0c8  mov     byte ptr [rax+18h], 1
0x18001b0cc  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Rrotate(std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x18001b0d1  mov     byte ptr [r10+18h], 1
0x18001b0d6  mov     rcx, [rbx+8]
0x18001b0da  test    rcx, rcx
0x18001b0dd  jz      short loc_18001B0E6
0x18001b0df  dec     rcx
0x18001b0e2  mov     [rbx+8], rcx
0x18001b0e6  mov     rbx, [rsp+28h+arg_0]
0x18001b0eb  mov     rax, r11
0x18001b0ee  add     rsp, 20h
0x18001b0f2  pop     rsi
0x18001b0f3  retn
```
