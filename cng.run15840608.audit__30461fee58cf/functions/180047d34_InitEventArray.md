# InitEventArray

- ea: `0x180047d34`
- end: `0x180047eae`
- name: `InitEventArray`
- size: `378`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180045220`

## callees

- `0x180003f70`
- `0x1800367b8`
- `0x180047d34`
- `0x180047eb4`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x180047e56`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180047e56`
- `ntoskrnl!ExEventObjectType` at `0x180047e1e`
- `ntoskrnl!ZwCreateEvent` at `0x180047e0b`
- `ntoskrnl!ZwCreateEvent` at `0x180047e0b`

## string_xrefs

- `0x180047e89`: `InitEventArray:: ZwCreateEvent failed`

## pseudocode

```c
__int64 __fastcall InitEventArray(__int64 *a1, _QWORD *a2, _DWORD *a3)
{
  void *v7; // rax
  unsigned int i; // ebx
  __int64 v9; // r14
  __int64 v10; // rsi
  NTSTATUS v11; // r15d
  void *v12; // rcx
  const wchar_t *v13; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-78h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+8h] BYREF

  if ( a1 )
  {
    v7 = (void *)MSCryptAlloc(64);
    *a1 = (__int64)v7;
    if ( v7 )
    {
      memset(v7, 0, 0x40u);
      for ( i = 0; i < 2; ++i )
      {
        v9 = *a1;
        v10 = 32LL * i;
        if ( (unsigned int)OpenLowestPossibleRegKey(a1, i) )
        {
          *(_QWORD *)(v10 + v9) = 0;
          *a3 = 1;
        }
        else
        {
          ++*a2;
        }
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 512;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v11 = ZwCreateEvent((PHANDLE)(v10 + v9 + 8), 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
        if ( v11 < 0 )
        {
          v13 = L"InitEventArray:: ZwCreateEvent failed";
          goto LABEL_15;
        }
        v12 = *(void **)(v10 + v9 + 8);
        Object = 0;
        v11 = ObReferenceObjectByHandle(v12, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &Object, 0);
        *(_QWORD *)(v10 + v9 + 16) = Object;
        if ( v11 < 0 )
        {
          v13 = L"InitEventArray:: ObReferenceObjectByHandle failed";
LABEL_15:
          SendTelemetry(v13);
          return (unsigned int)v11;
        }
      }
      return 0;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    SendTelemetry(L"InitEventArray:: pRegKeyNotifyRoot == nullptr");
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180047d34  push    rbx
0x180047d36  push    rbp
0x180047d37  push    rsi
0x180047d38  push    rdi
0x180047d39  push    r12
0x180047d3b  push    r13
0x180047d3d  push    r14
0x180047d3f  push    r15
0x180047d41  sub     rsp, 68h
0x180047d45  xor     r15d, r15d
0x180047d48  mov     r12, r8
0x180047d4b  mov     rbp, rdx
0x180047d4e  mov     rdi, rcx
0x180047d51  test    rcx, rcx
0x180047d54  jnz     short loc_180047D6C
0x180047d56  lea     rcx, aIniteventarray; "InitEventArray:: pRegKeyNotifyRoot == n"...
0x180047d5d  call    SendTelemetry
0x180047d62  mov     eax, 0C0000008h
0x180047d67  jmp     loc_180047E9C
0x180047d6c  mov     ebx, 40h ; '@'
0x180047d71  mov     ecx, ebx
0x180047d73  call    MSCryptAlloc
0x180047d78  mov     [rdi], rax
0x180047d7b  test    rax, rax
0x180047d7e  jnz     short loc_180047D8A
0x180047d80  mov     eax, 0C000000Dh
0x180047d85  jmp     loc_180047E9C
0x180047d8a  mov     r8, rbx; Size
0x180047d8d  xor     edx, edx; Val
0x180047d8f  mov     rcx, rax; void *
0x180047d92  call    memset
0x180047d97  mov     ebx, r15d
0x180047d9a  cmp     ebx, 2
0x180047d9d  jnb     loc_180047E9A
0x180047da3  mov     r14, [rdi]
0x180047da6  mov     edx, ebx
0x180047da8  mov     esi, ebx
0x180047daa  mov     rcx, rdi
0x180047dad  shl     rsi, 5
0x180047db1  call    OpenLowestPossibleRegKey
0x180047db6  test    eax, eax
0x180047db8  jz      short loc_180047DC8
0x180047dba  mov     [rsi+r14], r15
0x180047dbe  mov     dword ptr [r12], 1
0x180047dc6  jmp     short loc_180047DCC
0x180047dc8  inc     qword ptr [rbp+0]
0x180047dcc  xorps   xmm0, xmm0
0x180047dcf  mov     qword ptr [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180047dd8  lea     r13, [rsi+r14]
0x180047ddc  mov     qword ptr [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x180047de5  lea     rcx, [r13+8]; EventHandle
0x180047de9  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r15
0x180047dee  xor     r9d, r9d; EventType
0x180047df1  mov     [rsp+0A8h+ObjectAttributes.ObjectName], r15
0x180047df6  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180047dfb  mov     [rsp+0A8h+InitialState], r15b; InitialState
0x180047e00  mov     edx, 1F0003h; DesiredAccess
0x180047e05  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180047e0b  call    cs:__imp_ZwCreateEvent
0x180047e12  nop     dword ptr [rax+rax+00h]
0x180047e17  mov     r15d, eax
0x180047e1a  test    eax, eax
0x180047e1c  js      short loc_180047E89
0x180047e1e  mov     r8, cs:ExEventObjectType
0x180047e25  lea     rax, [rsp+0A8h+Object]
0x180047e2d  mov     rcx, [r13+8]; Handle
0x180047e31  xor     r9d, r9d; AccessMode
0x180047e34  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x180047e3d  mov     edx, 100002h; DesiredAccess
0x180047e42  mov     [rsp+0A8h+Object], 0
0x180047e4e  mov     r8, [r8]; ObjectType
0x180047e51  mov     qword ptr [rsp+0A8h+InitialState], rax; Object
0x180047e56  call    cs:__imp_ObReferenceObjectByHandle
0x180047e5d  nop     dword ptr [rax+rax+00h]
0x180047e62  mov     rcx, [rsp+0A8h+Object]
0x180047e6a  mov     r15d, eax
0x180047e6d  mov     [rsi+r14+10h], rcx
0x180047e72  test    eax, eax
0x180047e74  js      short loc_180047E80
0x180047e76  inc     ebx
0x180047e78  xor     r15d, r15d
0x180047e7b  jmp     loc_180047D9A
0x180047e80  lea     rcx, aIniteventarray_1; "InitEventArray:: ObReferenceObjectByHan"...
0x180047e87  jmp     short loc_180047E90
0x180047e89  lea     rcx, aIniteventarray_0; "InitEventArray:: ZwCreateEvent failed"
0x180047e90  call    SendTelemetry
0x180047e95  mov     eax, r15d
0x180047e98  jmp     short loc_180047E9C
0x180047e9a  xor     eax, eax
0x180047e9c  add     rsp, 68h
0x180047ea0  pop     r15
0x180047ea2  pop     r14
0x180047ea4  pop     r13
0x180047ea6  pop     r12
0x180047ea8  pop     rdi
0x180047ea9  pop     rsi
0x180047eaa  pop     rbp
0x180047eab  pop     rbx
0x180047eac  retn
```
