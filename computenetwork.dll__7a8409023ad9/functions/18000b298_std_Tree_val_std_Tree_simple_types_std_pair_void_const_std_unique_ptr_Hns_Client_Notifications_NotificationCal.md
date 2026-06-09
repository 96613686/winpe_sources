# std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *> *>,std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *> * const)

- ea: `0x18000b298`
- end: `0x18000b4c1`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a608`

## callees

- `0x18000b298`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x18000b298  mov     [rsp+arg_0], rbx
0x18000b29d  inc     qword ptr [rcx+8]
0x18000b2a1  mov     r11, rcx
0x18000b2a4  mov     r10, [rcx]
0x18000b2a7  mov     rax, [rdx]
0x18000b2aa  mov     [r8+8], rax
0x18000b2ae  cmp     rax, r10
0x18000b2b1  jnz     short loc_18000B2C8
0x18000b2b3  mov     [r10], r8
0x18000b2b6  mov     [r10+8], r8
0x18000b2ba  mov     [r10+10h], r8
0x18000b2be  mov     byte ptr [r8+18h], 1
0x18000b2c3  jmp     loc_18000B4B8
0x18000b2c8  xor     ebx, ebx
0x18000b2ca  cmp     [rdx+8], ebx
0x18000b2cd  jnz     short loc_18000B2DF
0x18000b2cf  mov     [rax+10h], r8
0x18000b2d3  cmp     rax, [r10+10h]
0x18000b2d7  jnz     short loc_18000B2EA
0x18000b2d9  mov     [r10+10h], r8
0x18000b2dd  jmp     short loc_18000B2EA
0x18000b2df  mov     [rax], r8
0x18000b2e2  cmp     rax, [r10]
0x18000b2e5  jnz     short loc_18000B2EA
0x18000b2e7  mov     [r10], r8
0x18000b2ea  mov     rax, [r8+8]
0x18000b2ee  mov     rdx, r8
0x18000b2f1  jmp     loc_18000B4A7
0x18000b2f6  mov     rcx, [rdx+8]
0x18000b2fa  mov     r9, [rcx+8]
0x18000b2fe  mov     rax, [r9]
0x18000b301  cmp     rcx, rax
0x18000b304  jnz     loc_18000B3CB
0x18000b30a  mov     rax, [r9+10h]
0x18000b30e  cmp     [rax+18h], bl
0x18000b311  jz      loc_18000B3D0
0x18000b317  mov     r9, [rcx+10h]
0x18000b31b  cmp     rdx, r9
0x18000b31e  jnz     short loc_18000B366
0x18000b320  mov     rax, [r9]
0x18000b323  mov     rdx, rcx
0x18000b326  mov     [rcx+10h], rax
0x18000b32a  mov     rax, [r9]
0x18000b32d  cmp     [rax+19h], bl
0x18000b330  jnz     short loc_18000B336
0x18000b332  mov     [rax+8], rcx
0x18000b336  mov     rax, [rcx+8]
0x18000b33a  mov     [r9+8], rax
0x18000b33e  mov     rax, [r11]
0x18000b341  cmp     rcx, [rax+8]
0x18000b345  jnz     short loc_18000B34D
0x18000b347  mov     [rax+8], r9
0x18000b34b  jmp     short loc_18000B35F
0x18000b34d  mov     rax, [rcx+8]
0x18000b351  cmp     rcx, [rax]
0x18000b354  jnz     short loc_18000B35B
0x18000b356  mov     [rax], r9
0x18000b359  jmp     short loc_18000B35F
0x18000b35b  mov     [rax+10h], r9
0x18000b35f  mov     [r9], rcx
0x18000b362  mov     [rcx+8], r9
0x18000b366  mov     rax, [rdx+8]
0x18000b36a  mov     byte ptr [rax+18h], 1
0x18000b36e  mov     rax, [rdx+8]
0x18000b372  mov     rcx, [rax+8]
0x18000b376  mov     [rcx+18h], bl
0x18000b379  mov     rax, [rdx+8]
0x18000b37d  mov     rcx, [rax+8]
0x18000b381  mov     r9, [rcx]
0x18000b384  mov     rax, [r9+10h]
0x18000b388  mov     [rcx], rax
0x18000b38b  mov     rax, [r9+10h]
0x18000b38f  cmp     [rax+19h], bl
0x18000b392  jnz     short loc_18000B398
0x18000b394  mov     [rax+8], rcx
0x18000b398  mov     rax, [rcx+8]
0x18000b39c  mov     [r9+8], rax
0x18000b3a0  mov     rax, [r11]
0x18000b3a3  cmp     rcx, [rax+8]
0x18000b3a7  jnz     short loc_18000B3AF
0x18000b3a9  mov     [rax+8], r9
0x18000b3ad  jmp     short loc_18000B3C2
0x18000b3af  mov     rax, [rcx+8]
0x18000b3b3  cmp     rcx, [rax+10h]
0x18000b3b7  jnz     short loc_18000B3BF
0x18000b3b9  mov     [rax+10h], r9
0x18000b3bd  jmp     short loc_18000B3C2
0x18000b3bf  mov     [rax], r9
0x18000b3c2  mov     [r9+10h], rcx
0x18000b3c6  jmp     loc_18000B49F
0x18000b3cb  cmp     [rax+18h], bl
0x18000b3ce  jnz     short loc_18000B3F0
0x18000b3d0  mov     byte ptr [rcx+18h], 1
0x18000b3d4  mov     byte ptr [rax+18h], 1
0x18000b3d8  mov     rax, [rdx+8]
0x18000b3dc  mov     rcx, [rax+8]
0x18000b3e0  mov     [rcx+18h], bl
0x18000b3e3  mov     rax, [rdx+8]
0x18000b3e7  mov     rdx, [rax+8]
0x18000b3eb  jmp     loc_18000B4A3
0x18000b3f0  mov     r9, [rcx]
0x18000b3f3  cmp     rdx, r9
0x18000b3f6  jnz     short loc_18000B441
0x18000b3f8  mov     rax, [r9+10h]
0x18000b3fc  mov     rdx, rcx
0x18000b3ff  mov     [rcx], rax
0x18000b402  mov     rax, [r9+10h]
0x18000b406  cmp     [rax+19h], bl
0x18000b409  jnz     short loc_18000B40F
0x18000b40b  mov     [rax+8], rcx
0x18000b40f  mov     rax, [rcx+8]
0x18000b413  mov     [r9+8], rax
0x18000b417  mov     rax, [r11]
0x18000b41a  cmp     rcx, [rax+8]
0x18000b41e  jnz     short loc_18000B426
0x18000b420  mov     [rax+8], r9
0x18000b424  jmp     short loc_18000B439
0x18000b426  mov     rax, [rcx+8]
0x18000b42a  cmp     rcx, [rax+10h]
0x18000b42e  jnz     short loc_18000B436
0x18000b430  mov     [rax+10h], r9
0x18000b434  jmp     short loc_18000B439
0x18000b436  mov     [rax], r9
0x18000b439  mov     [r9+10h], rcx
0x18000b43d  mov     [rcx+8], r9
0x18000b441  mov     rax, [rdx+8]
0x18000b445  mov     byte ptr [rax+18h], 1
0x18000b449  mov     rax, [rdx+8]
0x18000b44d  mov     rcx, [rax+8]
0x18000b451  mov     [rcx+18h], bl
0x18000b454  mov     rax, [rdx+8]
0x18000b458  mov     rcx, [rax+8]
0x18000b45c  mov     r9, [rcx+10h]
0x18000b460  mov     rax, [r9]
0x18000b463  mov     [rcx+10h], rax
0x18000b467  mov     rax, [r9]
0x18000b46a  cmp     [rax+19h], bl
0x18000b46d  jnz     short loc_18000B473
0x18000b46f  mov     [rax+8], rcx
0x18000b473  mov     rax, [rcx+8]
0x18000b477  mov     [r9+8], rax
0x18000b47b  mov     rax, [r11]
0x18000b47e  cmp     rcx, [rax+8]
0x18000b482  jnz     short loc_18000B48A
0x18000b484  mov     [rax+8], r9
0x18000b488  jmp     short loc_18000B49C
0x18000b48a  mov     rax, [rcx+8]
0x18000b48e  cmp     rcx, [rax]
0x18000b491  jnz     short loc_18000B498
0x18000b493  mov     [rax], r9
0x18000b496  jmp     short loc_18000B49C
0x18000b498  mov     [rax+10h], r9
0x18000b49c  mov     [r9], rcx
0x18000b49f  mov     [rcx+8], r9
0x18000b4a3  mov     rax, [rdx+8]
0x18000b4a7  cmp     [rax+18h], bl
0x18000b4aa  jz      loc_18000B2F6
0x18000b4b0  mov     rax, [r10+8]
0x18000b4b4  mov     byte ptr [rax+18h], 1
0x18000b4b8  mov     rbx, [rsp+arg_0]
0x18000b4bd  mov     rax, r8
0x18000b4c0  retn
```
