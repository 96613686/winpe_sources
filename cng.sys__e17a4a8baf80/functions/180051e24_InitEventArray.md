# InitEventArray

- ea: `0x180051e24`
- end: `0x180051f9e`
- name: `InitEventArray`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004f310`

## callees

- `0x18000e090`
- `0x180040828`
- `0x180051e24`
- `0x180051fa4`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x180051f46`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180051f46`
- `ntoskrnl!ExEventObjectType` at `0x180051f0e`
- `ntoskrnl!ZwCreateEvent` at `0x180051efb`
- `ntoskrnl!ZwCreateEvent` at `0x180051efb`

## string_xrefs

- `0x180051f79`: `InitEventArray:: ZwCreateEvent failed`

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
    v7 = (void *)MSCryptAlloc(64, a2);
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
0x180051e24  push    rbx
0x180051e26  push    rbp
0x180051e27  push    rsi
0x180051e28  push    rdi
0x180051e29  push    r12
0x180051e2b  push    r13
0x180051e2d  push    r14
0x180051e2f  push    r15
0x180051e31  sub     rsp, 68h
0x180051e35  xor     r15d, r15d
0x180051e38  mov     r12, r8
0x180051e3b  mov     rbp, rdx
0x180051e3e  mov     rdi, rcx
0x180051e41  test    rcx, rcx
0x180051e44  jnz     short loc_180051E5C
0x180051e46  lea     rcx, aIniteventarray; "InitEventArray:: pRegKeyNotifyRoot == n"...
0x180051e4d  call    SendTelemetry
0x180051e52  mov     eax, 0C0000008h
0x180051e57  jmp     loc_180051F8C
0x180051e5c  mov     ebx, 40h ; '@'
0x180051e61  mov     ecx, ebx
0x180051e63  call    MSCryptAlloc
0x180051e68  mov     [rdi], rax
0x180051e6b  test    rax, rax
0x180051e6e  jnz     short loc_180051E7A
0x180051e70  mov     eax, 0C000000Dh
0x180051e75  jmp     loc_180051F8C
0x180051e7a  mov     r8, rbx; Size
0x180051e7d  xor     edx, edx; Val
0x180051e7f  mov     rcx, rax; void *
0x180051e82  call    memset
0x180051e87  mov     ebx, r15d
0x180051e8a  cmp     ebx, 2
0x180051e8d  jnb     loc_180051F8A
0x180051e93  mov     r14, [rdi]
0x180051e96  mov     edx, ebx
0x180051e98  mov     esi, ebx
0x180051e9a  mov     rcx, rdi
0x180051e9d  shl     rsi, 5
0x180051ea1  call    OpenLowestPossibleRegKey
0x180051ea6  test    eax, eax
0x180051ea8  jz      short loc_180051EB8
0x180051eaa  mov     [rsi+r14], r15
0x180051eae  mov     dword ptr [r12], 1
0x180051eb6  jmp     short loc_180051EBC
0x180051eb8  inc     qword ptr [rbp+0]
0x180051ebc  xorps   xmm0, xmm0
0x180051ebf  mov     qword ptr [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180051ec8  lea     r13, [rsi+r14]
0x180051ecc  mov     qword ptr [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x180051ed5  lea     rcx, [r13+8]; EventHandle
0x180051ed9  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r15
0x180051ede  xor     r9d, r9d; EventType
0x180051ee1  mov     [rsp+0A8h+ObjectAttributes.ObjectName], r15
0x180051ee6  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180051eeb  mov     [rsp+0A8h+InitialState], r15b; InitialState
0x180051ef0  mov     edx, 1F0003h; DesiredAccess
0x180051ef5  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051efb  call    cs:__imp_ZwCreateEvent
0x180051f02  nop     dword ptr [rax+rax+00h]
0x180051f07  mov     r15d, eax
0x180051f0a  test    eax, eax
0x180051f0c  js      short loc_180051F79
0x180051f0e  mov     r8, cs:ExEventObjectType
0x180051f15  lea     rax, [rsp+0A8h+Object]
0x180051f1d  mov     rcx, [r13+8]; Handle
0x180051f21  xor     r9d, r9d; AccessMode
0x180051f24  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x180051f2d  mov     edx, 100002h; DesiredAccess
0x180051f32  mov     [rsp+0A8h+Object], 0
0x180051f3e  mov     r8, [r8]; ObjectType
0x180051f41  mov     qword ptr [rsp+0A8h+InitialState], rax; Object
0x180051f46  call    cs:__imp_ObReferenceObjectByHandle
0x180051f4d  nop     dword ptr [rax+rax+00h]
0x180051f52  mov     rcx, [rsp+0A8h+Object]
0x180051f5a  mov     r15d, eax
0x180051f5d  mov     [rsi+r14+10h], rcx
0x180051f62  test    eax, eax
0x180051f64  js      short loc_180051F70
0x180051f66  inc     ebx
0x180051f68  xor     r15d, r15d
0x180051f6b  jmp     loc_180051E8A
0x180051f70  lea     rcx, aIniteventarray_1; "InitEventArray:: ObReferenceObjectByHan"...
0x180051f77  jmp     short loc_180051F80
0x180051f79  lea     rcx, aIniteventarray_0; "InitEventArray:: ZwCreateEvent failed"
0x180051f80  call    SendTelemetry
0x180051f85  mov     eax, r15d
0x180051f88  jmp     short loc_180051F8C
0x180051f8a  xor     eax, eax
0x180051f8c  add     rsp, 68h
0x180051f90  pop     r15
0x180051f92  pop     r14
0x180051f94  pop     r13
0x180051f96  pop     r12
0x180051f98  pop     rdi
0x180051f99  pop     rsi
0x180051f9a  pop     rbp
0x180051f9b  pop     rbx
0x180051f9c  retn
```
