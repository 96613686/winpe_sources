# std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *>> &,std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *> *)

- ea: `0x180003e10`
- end: `0x180003e7c`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003e10`
- `0x180004108`

## callees

- `0x1800019d0`
- `0x180003e10`
- `0x180004240`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  Hns::Client::Notifications::NotificationCallbacks::NotificationContext *v6; // rdi
  void *v7; // rsi

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)v3[5];
      v7 = v3;
      v3 = (_QWORD *)*v3;
      if ( v6 )
      {
        Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(v6);
        operator delete(v6);
      }
      operator delete(v7);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x180003e10  push    rbx
0x180003e12  push    rbp
0x180003e13  push    rsi
0x180003e14  push    rdi
0x180003e15  push    r14
0x180003e17  sub     rsp, 20h
0x180003e1b  cmp     byte ptr [r8+19h], 0
0x180003e20  mov     rbx, r8
0x180003e23  mov     rbp, rdx
0x180003e26  mov     r14, rcx
0x180003e29  jnz     short loc_180003E71
0x180003e2b  mov     r8, [rbx+10h]
0x180003e2f  mov     rdx, rbp
0x180003e32  mov     rcx, r14
0x180003e35  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>> &,std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *> *)
0x180003e3a  mov     rdi, [rbx+28h]
0x180003e3e  mov     rsi, rbx
0x180003e41  mov     rbx, [rbx]
0x180003e44  test    rdi, rdi
0x180003e47  jz      short loc_180003E5E
0x180003e49  mov     rcx, rdi; this
0x180003e4c  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180003e51  mov     edx, 60h ; '`'; unsigned __int64
0x180003e56  mov     rcx, rdi; void *
0x180003e59  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003e5e  mov     edx, 30h ; '0'; unsigned __int64
0x180003e63  mov     rcx, rsi; void *
0x180003e66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003e6b  cmp     byte ptr [rbx+19h], 0
0x180003e6f  jz      short loc_180003E2B
0x180003e71  add     rsp, 20h
0x180003e75  pop     r14
0x180003e77  pop     rdi
0x180003e78  pop     rsi
0x180003e79  pop     rbp
0x180003e7a  pop     rbx
0x180003e7b  retn
```
