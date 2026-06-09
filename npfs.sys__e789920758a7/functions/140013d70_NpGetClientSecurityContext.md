# NpGetClientSecurityContext

- ea: `0x140013d70`
- end: `0x140013e1d`
- name: `NpGetClientSecurityContext`
- size: `173`
- prototype: `__int64 __fastcall(int, __int64, struct _KTHREAD *, struct _SECURITY_CLIENT_CONTEXT **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d314`
- `0x14000deb8`

## callees

- `0x140013d70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140013db9`
- `ntoskrnl!ExAllocatePool2` at `0x140013db9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013df1`
- `ntoskrnl!SeCreateClientSecurity` at `0x140013dda`
- `ntoskrnl!SeCreateClientSecurity` at `0x140013dda`

## pseudocode

```c
__int64 __fastcall NpGetClientSecurityContext(
        int a1,
        __int64 a2,
        struct _KTHREAD *a3,
        struct _SECURITY_CLIENT_CONTEXT **a4)
{
  struct _SECURITY_CLIENT_CONTEXT *v7; // rbx
  NTSTATUS ClientSecurity; // edi
  __int64 result; // rax
  struct _SECURITY_CLIENT_CONTEXT *Pool2; // rax

  if ( a1 || *(_BYTE *)(a2 + 20) != 1 || *(_QWORD *)(a2 + 264) == -1 )
  {
    v7 = 0;
    ClientSecurity = 0;
    goto LABEL_4;
  }
  Pool2 = (struct _SECURITY_CLIENT_CONTEXT *)ExAllocatePool2(257, 72, 1933996110);
  v7 = Pool2;
  if ( Pool2 )
  {
    ClientSecurity = SeCreateClientSecurity(a3, (PSECURITY_QUALITY_OF_SERVICE)(a2 + 12), 0, Pool2);
    if ( ClientSecurity < 0 )
    {
      ExFreePoolWithTag(v7, 0);
      result = (unsigned int)ClientSecurity;
      *a4 = 0;
      return result;
    }
LABEL_4:
    *a4 = v7;
    return (unsigned int)ClientSecurity;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140013d70  push    rbx
0x140013d72  push    rbp
0x140013d73  push    rsi
0x140013d74  push    rdi
0x140013d75  sub     rsp, 28h
0x140013d79  mov     rsi, r9
0x140013d7c  mov     rbp, r8
0x140013d7f  mov     rdi, rdx
0x140013d82  test    ecx, ecx
0x140013d84  jnz     short loc_140013D8C
0x140013d86  cmp     byte ptr [rdx+14h], 1
0x140013d8a  jz      short loc_140013D9F
0x140013d8c  xor     ebx, ebx
0x140013d8e  mov     edi, ebx
0x140013d90  mov     [rsi], rbx
0x140013d93  mov     eax, edi
0x140013d95  add     rsp, 28h
0x140013d99  pop     rdi
0x140013d9a  pop     rsi
0x140013d9b  pop     rbp
0x140013d9c  pop     rbx
0x140013d9d  retn
0x140013d9f  cmp     qword ptr [rdx+108h], 0FFFFFFFFFFFFFFFFh
0x140013da7  jz      short loc_140013D8C
0x140013da9  mov     edx, 48h ; 'H'
0x140013dae  mov     ecx, 101h
0x140013db3  mov     r8d, 7346704Eh
0x140013db9  call    cs:__imp_ExAllocatePool2
0x140013dc0  nop     dword ptr [rax+rax+00h]
0x140013dc5  mov     rbx, rax
0x140013dc8  test    rax, rax
0x140013dcb  jz      short loc_140013E0E
0x140013dcd  lea     rdx, [rdi+0Ch]; ClientSecurityQos
0x140013dd1  mov     r9, rax; ClientContext
0x140013dd4  xor     r8d, r8d; RemoteSession
0x140013dd7  mov     rcx, rbp; ClientThread
0x140013dda  call    cs:__imp_SeCreateClientSecurity
0x140013de1  nop     dword ptr [rax+rax+00h]
0x140013de6  mov     edi, eax
0x140013de8  test    eax, eax
0x140013dea  jns     short loc_140013D90
0x140013dec  xor     edx, edx; Tag
0x140013dee  mov     rcx, rbx; P
0x140013df1  call    cs:__imp_ExFreePoolWithTag
0x140013df8  nop     dword ptr [rax+rax+00h]
0x140013dfd  xor     ebx, ebx
0x140013dff  mov     eax, edi
0x140013e01  mov     [rsi], rbx
0x140013e04  add     rsp, 28h
0x140013e08  pop     rdi
0x140013e09  pop     rsi
0x140013e0a  pop     rbp
0x140013e0b  pop     rbx
0x140013e0c  retn
0x140013e0e  mov     eax, 0C000009Ah
0x140013e13  add     rsp, 28h
0x140013e17  pop     rdi
0x140013e18  pop     rsi
0x140013e19  pop     rbp
0x140013e1a  pop     rbx
0x140013e1b  retn
```
