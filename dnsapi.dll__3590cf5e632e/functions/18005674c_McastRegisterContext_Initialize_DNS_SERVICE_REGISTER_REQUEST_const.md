# McastRegisterContext::Initialize(_DNS_SERVICE_REGISTER_REQUEST const *)

- ea: `0x18005674c`
- end: `0x180056820`
- name: `?Initialize@McastRegisterContext@@QEAAJPEBU_DNS_SERVICE_REGISTER_REQUEST@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(McastRegisterContext *__hidden this, const struct _DNS_SERVICE_REGISTER_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180056600`

## callees

- `0x18002a160`
- `0x18005674c`
- `0x180056830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800567c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800567c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800567ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800567de`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800567ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800567de`

## pseudocode

```c
int __fastcall McastRegisterContext::Initialize(
        McastRegisterContext *this,
        const struct _DNS_SERVICE_REGISTER_REQUEST *a2)
{
  __int64 StringCopy_W; // rax
  HANDLE EventW; // rax
  HANDLE v7; // rax
  __int64 v8; // rax

  *((_QWORD *)this + 10) = *((_QWORD *)a2 + 3);
  *((_QWORD *)this + 16) = *((_QWORD *)a2 + 2);
  *((_DWORD *)this + 39) = *((_DWORD *)a2 + 1);
  *((_DWORD *)this + 22) = *(_DWORD *)a2;
  StringCopy_W = Dns_CreateStringCopy_W(**((void ***)a2 + 1));
  *((_QWORD *)this + 15) = StringCopy_W;
  if ( !StringCopy_W )
    return 14;
  *((_QWORD *)this + 18) = *((_QWORD *)a2 + 4);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 20) = EventW;
  if ( !EventW )
    return GetLastError();
  v7 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 21) = v7;
  if ( !v7 )
    return GetLastError();
  v8 = DnsServiceCopyInstance(*((_QWORD *)a2 + 1));
  *((_QWORD *)this + 17) = v8;
  return v8 != 0 ? 0 : 0xE;
}

```

## disassembly

```asm
0x18005674c  mov     [rsp+arg_0], rbx
0x180056751  push    rdi
0x180056752  sub     rsp, 20h
0x180056756  mov     rax, [rdx+18h]
0x18005675a  mov     rbx, rcx
0x18005675d  mov     [rcx+50h], rax
0x180056761  mov     rdi, rdx
0x180056764  mov     rax, [rdx+10h]
0x180056768  mov     [rcx+80h], rax
0x18005676f  mov     eax, [rdx+4]
0x180056772  mov     [rcx+9Ch], eax
0x180056778  mov     eax, [rdx]
0x18005677a  mov     [rcx+58h], eax
0x18005677d  mov     rcx, [rdx+8]
0x180056781  mov     rcx, [rcx]; Src
0x180056784  call    Dns_CreateStringCopy_W
0x180056789  mov     [rbx+78h], rax
0x18005678d  test    rax, rax
0x180056790  jnz     short loc_180056799
0x180056792  mov     eax, 0Eh
0x180056797  jmp     short loc_180056814
0x180056799  mov     rax, [rdi+20h]
0x18005679d  xor     r9d, r9d; lpName
0x1800567a0  xor     r8d, r8d; bInitialState
0x1800567a3  mov     [rbx+90h], rax
0x1800567aa  xor     edx, edx; bManualReset
0x1800567ac  xor     ecx, ecx; lpEventAttributes
0x1800567ae  call    cs:__imp_CreateEventW
0x1800567b5  nop     dword ptr [rax+rax+00h]
0x1800567ba  mov     [rbx+0A0h], rax
0x1800567c1  test    rax, rax
0x1800567c4  jnz     short loc_1800567D4
0x1800567c6  call    cs:__imp_GetLastError
0x1800567cd  nop     dword ptr [rax+rax+00h]
0x1800567d2  jmp     short loc_180056814
0x1800567d4  xor     r9d, r9d; lpName
0x1800567d7  xor     r8d, r8d; bInitialState
0x1800567da  xor     edx, edx; bManualReset
0x1800567dc  xor     ecx, ecx; lpEventAttributes
0x1800567de  call    cs:__imp_CreateEventW
0x1800567e5  nop     dword ptr [rax+rax+00h]
0x1800567ea  mov     [rbx+0A8h], rax
0x1800567f1  test    rax, rax
0x1800567f4  jz      short loc_1800567C6
0x1800567f6  mov     rcx, [rdi+8]
0x1800567fa  call    DnsServiceCopyInstance
0x1800567ff  mov     [rbx+88h], rax
0x180056806  neg     rax
0x180056809  mov     eax, 0Eh
0x18005680e  sbb     ecx, ecx
0x180056810  not     ecx
0x180056812  and     eax, ecx
0x180056814  mov     rbx, [rsp+28h+arg_0]
0x180056819  add     rsp, 20h
0x18005681d  pop     rdi
0x18005681e  retn
```
