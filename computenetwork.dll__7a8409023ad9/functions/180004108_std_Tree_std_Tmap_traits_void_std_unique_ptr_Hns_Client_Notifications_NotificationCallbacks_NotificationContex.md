# std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>,0>>(void)

- ea: `0x180004108`
- end: `0x180004178`
- name: `??1?$_Tree@V?$_Tmap_traits@PEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e410`
- `0x18000e430`
- `0x18000e450`

## callees

- `0x1800019d0`
- `0x180003e10`
- `0x180004108`
- `0x180004240`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rbx
  Hns::Client::Notifications::NotificationCallbacks::NotificationContext *v3; // rsi
  void *v4; // rbp

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(
      a1,
      a1,
      v2[2]);
    v3 = (Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)v2[5];
    v4 = v2;
    v2 = (_QWORD *)*v2;
    if ( v3 )
    {
      Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(v3);
      operator delete(v3);
    }
    operator delete(v4);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x180004108  push    rbx
0x18000410a  push    rbp
0x18000410b  push    rsi
0x18000410c  push    rdi
0x18000410d  sub     rsp, 28h
0x180004111  mov     rax, [rcx]
0x180004114  mov     rdi, rcx
0x180004117  mov     rbx, [rax+8]
0x18000411b  jmp     short loc_18000415D
0x18000411d  mov     r8, [rbx+10h]
0x180004121  mov     rdx, rdi
0x180004124  mov     rcx, rdi
0x180004127  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>> &,std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *> *)
0x18000412c  mov     rsi, [rbx+28h]
0x180004130  mov     rbp, rbx
0x180004133  mov     rbx, [rbx]
0x180004136  test    rsi, rsi
0x180004139  jz      short loc_180004150
0x18000413b  mov     rcx, rsi; this
0x18000413e  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180004143  mov     edx, 60h ; '`'; unsigned __int64
0x180004148  mov     rcx, rsi; void *
0x18000414b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004150  mov     edx, 30h ; '0'; unsigned __int64
0x180004155  mov     rcx, rbp; void *
0x180004158  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000415d  cmp     byte ptr [rbx+19h], 0
0x180004161  jz      short loc_18000411D
0x180004163  mov     rcx, [rdi]; void *
0x180004166  mov     edx, 30h ; '0'; unsigned __int64
0x18000416b  add     rsp, 28h
0x18000416f  pop     rdi
0x180004170  pop     rsi
0x180004171  pop     rbp
0x180004172  pop     rbx
0x180004173  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
