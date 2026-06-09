# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(void)

- ea: `0x18002b310`
- end: `0x18002b4ba`
- name: `??1BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ`
- size: `426`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002b198`
- `0x18002b240`
- `0x18002b4c0`
- `0x18002c060`

## callees

- `0x180001b94`
- `0x18002b0e8`
- `0x18002b310`
- `0x18002e1d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b466`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b466`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *this)
{
  void **v1; // rsi
  __int64 *j; // rbx
  _QWORD *v4; // rdi
  __int64 **v5; // rax
  __int64 *i; // rax
  __int64 *v7; // rcx
  _QWORD *v8; // rbx
  void *v9; // rcx
  __int64 v10; // rcx
  void *v11; // rbx
  _QWORD **v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *v14; // rbx
  void *v15; // rcx
  _QWORD **v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rbx

  v1 = (void **)((char *)this + 56);
  j = (__int64 *)**((_QWORD **)this + 7);
  while ( 1 )
  {
    v4 = *v1;
    if ( j == *v1 )
      break;
    operator delete((void *)j[5], (const struct std::nothrow_t *)1);
    j[5] = 0;
    v5 = (__int64 **)j[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = (__int64 *)j[1]; !*((_BYTE *)i + 25) && j == (__int64 *)i[2]; i = (__int64 *)i[1] )
        j = i;
      j = i;
    }
    else
    {
      v7 = *v5;
      for ( j = (__int64 *)j[2]; !*((_BYTE *)v7 + 25); v7 = (__int64 *)*v7 )
        j = v7;
    }
  }
  v8 = (_QWORD *)v4[1];
  while ( !*((_BYTE *)v8 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(
      v1,
      v1,
      v8[2]);
    v9 = v8;
    v8 = (_QWORD *)*v8;
    operator delete(v9, (const struct std::nothrow_t *)0x30);
  }
  v4[1] = v4;
  *v4 = v4;
  v4[2] = v4;
  v1[1] = 0;
  while ( *((_QWORD *)this + 1) )
  {
    v10 = *(_QWORD *)(*(_QWORD *)this + 8LL);
    v11 = *(void **)(v10 + 16);
    if ( v11 )
    {
      Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(*(PTP_TIMER **)(v10 + 16));
      operator delete(v11, (const struct std::nothrow_t *)0x810);
    }
    v12 = *(_QWORD ***)(*(_QWORD *)this + 8LL);
    v13 = *v12;
    --*((_QWORD *)this + 1);
    *v12[1] = v13;
    v13[1] = v12[1];
    operator delete(v12, (const struct std::nothrow_t *)0x18);
  }
  v14 = (_QWORD *)*((_QWORD *)*v1 + 1);
  while ( !*((_BYTE *)v14 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(
      v1,
      v1,
      v14[2]);
    v15 = v14;
    v14 = (_QWORD *)*v14;
    operator delete(v15, (const struct std::nothrow_t *)0x30);
  }
  operator delete(*v1, (const struct std::nothrow_t *)0x30);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v16 = *(_QWORD ***)this;
  **(_QWORD **)(*(_QWORD *)this + 8LL) = 0;
  v17 = *v16;
  if ( v17 )
  {
    do
    {
      v18 = (_QWORD *)*v17;
      operator delete(v17, (const struct std::nothrow_t *)0x18);
      v17 = v18;
    }
    while ( v18 );
  }
  operator delete(*(void **)this, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x18002b310  mov     [rsp+arg_0], rbx
0x18002b315  mov     [rsp+arg_8], rbp
0x18002b31a  mov     [rsp+arg_10], rsi
0x18002b31f  push    rdi
0x18002b320  push    r14
0x18002b322  push    r15
0x18002b324  sub     rsp, 20h
0x18002b328  lea     rsi, [rcx+38h]
0x18002b32c  mov     r14, rcx
0x18002b32f  mov     rbx, [rsi]
0x18002b332  xor     ebp, ebp
0x18002b334  mov     rbx, [rbx]
0x18002b337  mov     rdi, [rsi]
0x18002b33a  cmp     rbx, rdi
0x18002b33d  jz      short loc_18002B396
0x18002b33f  mov     rcx, [rbx+28h]; void *
0x18002b343  mov     edx, 1; struct std::nothrow_t *
0x18002b348  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b34d  mov     [rbx+28h], rbp
0x18002b351  mov     rax, [rbx+10h]
0x18002b355  cmp     [rax+19h], bpl
0x18002b359  jz      short loc_18002B379
0x18002b35b  mov     rax, [rbx+8]
0x18002b35f  jmp     short loc_18002B36E
0x18002b361  cmp     rbx, [rax+10h]
0x18002b365  jnz     short loc_18002B374
0x18002b367  mov     rbx, rax
0x18002b36a  mov     rax, [rax+8]
0x18002b36e  cmp     [rax+19h], bpl
0x18002b372  jz      short loc_18002B361
0x18002b374  mov     rbx, rax
0x18002b377  jmp     short loc_18002B337
0x18002b379  mov     rcx, [rax]
0x18002b37c  mov     rbx, rax
0x18002b37f  cmp     [rcx+19h], bpl
0x18002b383  jnz     short loc_18002B337
0x18002b385  mov     rax, [rcx]
0x18002b388  mov     rbx, rcx
0x18002b38b  mov     rcx, rax
0x18002b38e  cmp     [rax+19h], bpl
0x18002b392  jz      short loc_18002B385
0x18002b394  jmp     short loc_18002B337
0x18002b396  mov     rbx, [rdi+8]
0x18002b39a  mov     r15d, 30h ; '0'
0x18002b3a0  jmp     short loc_18002B3BF
0x18002b3a2  mov     r8, [rbx+10h]
0x18002b3a6  mov     rdx, rsi
0x18002b3a9  mov     rcx, rsi
0x18002b3ac  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAD@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *> *)
0x18002b3b1  mov     rcx, rbx; void *
0x18002b3b4  mov     rdx, r15; struct std::nothrow_t *
0x18002b3b7  mov     rbx, [rbx]
0x18002b3ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b3bf  cmp     [rbx+19h], bpl
0x18002b3c3  jz      short loc_18002B3A2
0x18002b3c5  mov     [rdi+8], rdi
0x18002b3c9  mov     [rdi], rdi
0x18002b3cc  mov     [rdi+10h], rdi
0x18002b3d0  mov     edi, 18h
0x18002b3d5  mov     [rsi+8], rbp
0x18002b3d9  cmp     [r14+8], rbp
0x18002b3dd  jz      short loc_18002B42B
0x18002b3df  mov     rax, [r14]
0x18002b3e2  mov     rcx, [rax+8]
0x18002b3e6  mov     rbx, [rcx+10h]
0x18002b3ea  test    rbx, rbx
0x18002b3ed  jz      short loc_18002B404
0x18002b3ef  mov     rcx, rbx; this
0x18002b3f2  call    ??1BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(void)
0x18002b3f7  mov     edx, 810h; struct std::nothrow_t *
0x18002b3fc  mov     rcx, rbx; void *
0x18002b3ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b404  mov     rax, [r14]
0x18002b407  mov     rcx, [rax+8]; void *
0x18002b40b  mov     rdx, [rcx]
0x18002b40e  dec     qword ptr [r14+8]
0x18002b412  mov     rax, [rcx+8]
0x18002b416  mov     [rax], rdx
0x18002b419  mov     rax, [rcx+8]
0x18002b41d  mov     [rdx+8], rax
0x18002b421  mov     rdx, rdi; struct std::nothrow_t *
0x18002b424  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b429  jmp     short loc_18002B3D9
0x18002b42b  mov     rax, [rsi]
0x18002b42e  mov     rbx, [rax+8]
0x18002b432  jmp     short loc_18002B451
0x18002b434  mov     r8, [rbx+10h]
0x18002b438  mov     rdx, rsi
0x18002b43b  mov     rcx, rsi
0x18002b43e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAD@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *> *)
0x18002b443  mov     rcx, rbx; void *
0x18002b446  mov     rdx, r15; struct std::nothrow_t *
0x18002b449  mov     rbx, [rbx]
0x18002b44c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b451  cmp     [rbx+19h], bpl
0x18002b455  jz      short loc_18002B434
0x18002b457  mov     rcx, [rsi]; void *
0x18002b45a  mov     rdx, r15; struct std::nothrow_t *
0x18002b45d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b462  lea     rcx, [r14+10h]; lpCriticalSection
0x18002b466  call    cs:__imp_DeleteCriticalSection
0x18002b46d  nop     dword ptr [rax+rax+00h]
0x18002b472  mov     rcx, [r14]
0x18002b475  mov     rax, [rcx+8]
0x18002b479  mov     [rax], rbp
0x18002b47c  mov     rcx, [rcx]; void *
0x18002b47f  test    rcx, rcx
0x18002b482  jz      short loc_18002B497
0x18002b484  mov     rbx, [rcx]
0x18002b487  mov     rdx, rdi; struct std::nothrow_t *
0x18002b48a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b48f  mov     rcx, rbx
0x18002b492  test    rbx, rbx
0x18002b495  jnz     short loc_18002B484
0x18002b497  mov     rcx, [r14]; void *
0x18002b49a  mov     rdx, rdi; struct std::nothrow_t *
0x18002b49d  mov     rbx, [rsp+38h+arg_0]
0x18002b4a2  mov     rbp, [rsp+38h+arg_8]
0x18002b4a7  mov     rsi, [rsp+38h+arg_10]
0x18002b4ac  add     rsp, 20h
0x18002b4b0  pop     r15
0x18002b4b2  pop     r14
0x18002b4b4  pop     rdi
0x18002b4b5  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
