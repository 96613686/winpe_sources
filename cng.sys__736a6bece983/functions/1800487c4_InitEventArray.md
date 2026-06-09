# InitEventArray

- ea: `0x1800487c4`
- end: `0x18004893e`
- name: `InitEventArray`
- size: `378`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180045cb0`

## callees

- `0x180003f70`
- `0x1800372b8`
- `0x1800487c4`
- `0x180048944`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800488e6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800488e6`
- `ntoskrnl!ExEventObjectType` at `0x1800488ae`
- `ntoskrnl!ZwCreateEvent` at `0x18004889b`
- `ntoskrnl!ZwCreateEvent` at `0x18004889b`

## string_xrefs

- `0x180048919`: `InitEventArray:: ZwCreateEvent failed`

## pseudocode

```c
__int64 __fastcall InitEventArray(__int64 *a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  void *v8; // rax
  unsigned int i; // ebx
  __int64 v10; // r14
  __int64 v11; // rsi
  NTSTATUS v12; // r15d
  void *v13; // rcx
  const wchar_t *v14; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-78h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+8h] BYREF

  if ( a1 )
  {
    v8 = (void *)MSCryptAlloc(64, a2, a3, a4);
    *a1 = (__int64)v8;
    if ( v8 )
    {
      memset(v8, 0, 0x40u);
      for ( i = 0; i < 2; ++i )
      {
        v10 = *a1;
        v11 = 32LL * i;
        if ( (unsigned int)OpenLowestPossibleRegKey(a1, i) )
        {
          *(_QWORD *)(v11 + v10) = 0;
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
        v12 = ZwCreateEvent((PHANDLE)(v11 + v10 + 8), 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
        if ( v12 < 0 )
        {
          v14 = L"InitEventArray:: ZwCreateEvent failed";
          goto LABEL_15;
        }
        v13 = *(void **)(v11 + v10 + 8);
        Object = 0;
        v12 = ObReferenceObjectByHandle(v13, 0x100002u, (POBJECT_TYPE)ExEventObjectType, 0, &Object, 0);
        *(_QWORD *)(v11 + v10 + 16) = Object;
        if ( v12 < 0 )
        {
          v14 = L"InitEventArray:: ObReferenceObjectByHandle failed";
LABEL_15:
          SendTelemetry(v14);
          return (unsigned int)v12;
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
0x1800487c4  push    rbx
0x1800487c6  push    rbp
0x1800487c7  push    rsi
0x1800487c8  push    rdi
0x1800487c9  push    r12
0x1800487cb  push    r13
0x1800487cd  push    r14
0x1800487cf  push    r15
0x1800487d1  sub     rsp, 68h
0x1800487d5  xor     r15d, r15d
0x1800487d8  mov     r12, r8
0x1800487db  mov     rbp, rdx
0x1800487de  mov     rdi, rcx
0x1800487e1  test    rcx, rcx
0x1800487e4  jnz     short loc_1800487FC
0x1800487e6  lea     rcx, aIniteventarray; "InitEventArray:: pRegKeyNotifyRoot == n"...
0x1800487ed  call    SendTelemetry
0x1800487f2  mov     eax, 0C0000008h
0x1800487f7  jmp     loc_18004892C
0x1800487fc  mov     ebx, 40h ; '@'
0x180048801  mov     ecx, ebx
0x180048803  call    MSCryptAlloc
0x180048808  mov     [rdi], rax
0x18004880b  test    rax, rax
0x18004880e  jnz     short loc_18004881A
0x180048810  mov     eax, 0C000000Dh
0x180048815  jmp     loc_18004892C
0x18004881a  mov     r8, rbx; Size
0x18004881d  xor     edx, edx; Val
0x18004881f  mov     rcx, rax; void *
0x180048822  call    memset
0x180048827  mov     ebx, r15d
0x18004882a  cmp     ebx, 2
0x18004882d  jnb     loc_18004892A
0x180048833  mov     r14, [rdi]
0x180048836  mov     edx, ebx
0x180048838  mov     esi, ebx
0x18004883a  mov     rcx, rdi
0x18004883d  shl     rsi, 5
0x180048841  call    OpenLowestPossibleRegKey
0x180048846  test    eax, eax
0x180048848  jz      short loc_180048858
0x18004884a  mov     [rsi+r14], r15
0x18004884e  mov     dword ptr [r12], 1
0x180048856  jmp     short loc_18004885C
0x180048858  inc     qword ptr [rbp+0]
0x18004885c  xorps   xmm0, xmm0
0x18004885f  mov     qword ptr [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180048868  lea     r13, [rsi+r14]
0x18004886c  mov     qword ptr [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x180048875  lea     rcx, [r13+8]; EventHandle
0x180048879  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r15
0x18004887e  xor     r9d, r9d; EventType
0x180048881  mov     [rsp+0A8h+ObjectAttributes.ObjectName], r15
0x180048886  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18004888b  mov     [rsp+0A8h+InitialState], r15b; InitialState
0x180048890  mov     edx, 1F0003h; DesiredAccess
0x180048895  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004889b  call    cs:__imp_ZwCreateEvent
0x1800488a2  nop     dword ptr [rax+rax+00h]
0x1800488a7  mov     r15d, eax
0x1800488aa  test    eax, eax
0x1800488ac  js      short loc_180048919
0x1800488ae  mov     r8, cs:ExEventObjectType
0x1800488b5  lea     rax, [rsp+0A8h+Object]
0x1800488bd  mov     rcx, [r13+8]; Handle
0x1800488c1  xor     r9d, r9d; AccessMode
0x1800488c4  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x1800488cd  mov     edx, 100002h; DesiredAccess
0x1800488d2  mov     [rsp+0A8h+Object], 0
0x1800488de  mov     r8, [r8]; ObjectType
0x1800488e1  mov     qword ptr [rsp+0A8h+InitialState], rax; Object
0x1800488e6  call    cs:__imp_ObReferenceObjectByHandle
0x1800488ed  nop     dword ptr [rax+rax+00h]
0x1800488f2  mov     rcx, [rsp+0A8h+Object]
0x1800488fa  mov     r15d, eax
0x1800488fd  mov     [rsi+r14+10h], rcx
0x180048902  test    eax, eax
0x180048904  js      short loc_180048910
0x180048906  inc     ebx
0x180048908  xor     r15d, r15d
0x18004890b  jmp     loc_18004882A
0x180048910  lea     rcx, aIniteventarray_1; "InitEventArray:: ObReferenceObjectByHan"...
0x180048917  jmp     short loc_180048920
0x180048919  lea     rcx, aIniteventarray_0; "InitEventArray:: ZwCreateEvent failed"
0x180048920  call    SendTelemetry
0x180048925  mov     eax, r15d
0x180048928  jmp     short loc_18004892C
0x18004892a  xor     eax, eax
0x18004892c  add     rsp, 68h
0x180048930  pop     r15
0x180048932  pop     r14
0x180048934  pop     r13
0x180048936  pop     r12
0x180048938  pop     rdi
0x180048939  pop     rsi
0x18004893a  pop     rbp
0x18004893b  pop     rbx
0x18004893c  retn
```
