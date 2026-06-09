# CMSMQMessage::put_Extension(tagVARIANT)

- ea: `0x1800199e0`
- end: `0x180019acd`
- name: `?put_Extension@CMSMQMessage@@UEAAJUtagVARIANT@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CMSMQMessage *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x1800199e0`
- `0x180026c48`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180019a3b`
- `KERNEL32!LeaveCriticalSection` at `0x180019a6d`
- `KERNEL32!LeaveCriticalSection` at `0x180019aa8`
- `KERNEL32!LeaveCriticalSection` at `0x180019ab4`
- `KERNEL32!LeaveCriticalSection` at `0x180019a3b`
- `KERNEL32!LeaveCriticalSection` at `0x180019a6d`
- `KERNEL32!LeaveCriticalSection` at `0x180019aa8`
- `KERNEL32!LeaveCriticalSection` at `0x180019ab4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQMessage::put_Extension(CMSMQMessage *this, struct tagVARIANT *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  unsigned int ErrorHelper; // ebx
  HRESULT SafeArrayDataOfVariant; // eax
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int8 *v9; // [rsp+38h] [rbp+10h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQMessage *)((char *)this + 72));
  v9 = 0;
  v8 = 0;
  if ( ((a2->vt - 8209) & 0xBFFF) != 0 )
  {
    ErrorHelper = CreateErrorHelper(2147942487LL, 1);
    LeaveCriticalSection(v4);
    return ErrorHelper;
  }
  SafeArrayDataOfVariant = GetSafeArrayDataOfVariant(a2, &v9, &v8);
  if ( SafeArrayDataOfVariant < 0
    || (SafeArrayDataOfVariant = (*(__int64 (__fastcall **)(char *, unsigned __int8 *, _QWORD))(*((_QWORD *)this + 334)
                                                                                              + 64LL))(
                                   (char *)this + 2672,
                                   v9,
                                   v8),
        SafeArrayDataOfVariant < 0) )
  {
    ErrorHelper = CreateErrorHelper((unsigned int)SafeArrayDataOfVariant, 1);
    LeaveCriticalSection(v4);
    return ErrorHelper;
  }
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x1800199e0  mov     [rsp+arg_10], rbx
0x1800199e5  mov     [rsp+arg_18], rsi
0x1800199ea  push    rdi
0x1800199eb  sub     rsp, 20h
0x1800199ef  mov     rbx, rdx
0x1800199f2  mov     rsi, rcx
0x1800199f5  lea     rdi, [rcx+48h]
0x1800199f9  mov     rcx, rdi; this
0x1800199fc  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180019a01  mov     [rsp+28h+arg_8], 0
0x180019a0a  mov     [rsp+28h+arg_0], 0
0x180019a12  mov     ecx, 2011h
0x180019a17  movzx   eax, word ptr [rbx]
0x180019a1a  sub     ax, cx
0x180019a1d  mov     ecx, 0BFFFh
0x180019a22  test    cx, ax
0x180019a25  jz      short loc_180019A46
0x180019a27  mov     edx, 1
0x180019a2c  mov     ecx, 80070057h
0x180019a31  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180019a36  mov     ebx, eax
0x180019a38  mov     rcx, rdi; lpCriticalSection
0x180019a3b  call    cs:__imp_LeaveCriticalSection
0x180019a41  nop
0x180019a42  mov     eax, ebx
0x180019a44  jmp     short loc_180019ABD
0x180019a46  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x180019a4b  lea     rdx, [rsp+28h+arg_8]; unsigned __int8 **
0x180019a50  mov     rcx, rbx; struct tagVARIANT *
0x180019a53  call    ?GetSafeArrayDataOfVariant@@YAJPEAUtagVARIANT@@PEAPEAEPEAK@Z; GetSafeArrayDataOfVariant(tagVARIANT *,uchar * *,ulong *)
0x180019a58  test    eax, eax
0x180019a5a  jns     short loc_180019A76
0x180019a5c  mov     edx, 1
0x180019a61  mov     ecx, eax
0x180019a63  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180019a68  mov     ebx, eax
0x180019a6a  mov     rcx, rdi; lpCriticalSection
0x180019a6d  call    cs:__imp_LeaveCriticalSection
0x180019a73  nop
0x180019a74  jmp     short loc_180019A42
0x180019a76  lea     rcx, [rsi+0A70h]
0x180019a7d  mov     rax, [rcx]
0x180019a80  mov     r8d, [rsp+28h+arg_0]
0x180019a85  mov     rdx, [rsp+28h+arg_8]
0x180019a8a  mov     rax, [rax+40h]
0x180019a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a93  test    eax, eax
0x180019a95  jns     short loc_180019AB1
0x180019a97  mov     edx, 1
0x180019a9c  mov     ecx, eax
0x180019a9e  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180019aa3  mov     ebx, eax
0x180019aa5  mov     rcx, rdi; lpCriticalSection
0x180019aa8  call    cs:__imp_LeaveCriticalSection
0x180019aae  nop
0x180019aaf  jmp     short loc_180019A42
0x180019ab1  mov     rcx, rdi; lpCriticalSection
0x180019ab4  call    cs:__imp_LeaveCriticalSection
0x180019aba  nop
0x180019abb  xor     eax, eax
0x180019abd  mov     rbx, [rsp+28h+arg_10]
0x180019ac2  mov     rsi, [rsp+28h+arg_18]
0x180019ac7  add     rsp, 20h
0x180019acb  pop     rdi
0x180019acc  retn
```
