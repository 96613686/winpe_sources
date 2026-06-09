# CActiveXInstallSecurityManager::ProcessUrlAction(ulong,uchar *,ulong,uchar *,ulong,ulong,ulong)

- ea: `0x14000be80`
- end: `0x14000beec`
- name: `?ProcessUrlAction@CActiveXInstallSecurityManager@@UEAAJKPEAEK0KKK@Z`
- size: `108`
- prototype: `__int64 __fastcall(CActiveXInstallSecurityManager *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000be80`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::ProcessUrlAction(
        CActiveXInstallSecurityManager *this,
        unsigned int a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  __int64 result; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx

  result = 2147500037LL;
  v10 = *((_QWORD *)this + 2);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 3);
    if ( v11 )
      return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int8 *, int, unsigned __int8 *, unsigned int, unsigned int, unsigned int))(*(_QWORD *)v11 + 56LL))(
               v11,
               v10,
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8);
  }
  return result;
}

```

## disassembly

```asm
0x14000be80  sub     rsp, 58h
0x14000be84  mov     r11d, edx
0x14000be87  mov     eax, 80004005h
0x14000be8c  mov     rdx, [rcx+10h]
0x14000be90  test    rdx, rdx
0x14000be93  jz      short loc_14000BEE6
0x14000be95  mov     rcx, [rcx+18h]
0x14000be99  test    rcx, rcx
0x14000be9c  jz      short loc_14000BEE6
0x14000be9e  mov     rax, [rcx]
0x14000bea1  mov     r10, [rax+38h]
0x14000bea5  mov     eax, [rsp+58h+arg_38]
0x14000beac  mov     [rsp+58h+var_18], eax
0x14000beb0  mov     eax, [rsp+58h+arg_30]
0x14000beb7  mov     [rsp+58h+var_20], eax
0x14000bebb  mov     eax, [rsp+58h+arg_28]
0x14000bec2  mov     [rsp+58h+var_28], eax
0x14000bec6  mov     rax, [rsp+58h+arg_20]
0x14000bece  mov     [rsp+58h+var_30], rax
0x14000bed3  mov     rax, r10
0x14000bed6  mov     [rsp+58h+var_38], r9d
0x14000bedb  mov     r9, r8
0x14000bede  mov     r8d, r11d
0x14000bee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bee6  add     rsp, 58h
0x14000beea  retn
```
