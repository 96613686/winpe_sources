# DusmDhcp::UnregisterFromNsiNotifications(void)

- ea: `0x18003d564`
- end: `0x18003d5af`
- name: `?UnregisterFromNsiNotifications@DusmDhcp@@AEAAXXZ`
- size: `75`
- prototype: `void __fastcall(DusmDhcp *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003d464`
- `0x18003d504`

## callees

- `0x18003d564`

## import_xrefs

- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003d586`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003d586`
- `WINNSI!NsiDisconnectFromServer` at `0x18003d59c`
- `WINNSI!NsiDisconnectFromServer` at `0x18003d59c`

## pseudocode

```c
void __fastcall DusmDhcp::UnregisterFromNsiNotifications(DusmDhcp *this)
{
  if ( *((_QWORD *)this + 1) )
  {
    NsiRpcDeregisterChangeNotification(*(_QWORD *)this, &NPI_MS_IPV4_MODULEID, 10);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    NsiDisconnectFromServer();
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18003d564  push    rbx
0x18003d566  sub     rsp, 20h
0x18003d56a  mov     r9, [rcx+8]
0x18003d56e  mov     rbx, rcx
0x18003d571  test    r9, r9
0x18003d574  jz      short loc_18003D594
0x18003d576  mov     rcx, [rcx]
0x18003d579  lea     rdx, NPI_MS_IPV4_MODULEID
0x18003d580  mov     r8d, 0Ah
0x18003d586  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18003d58c  mov     qword ptr [rbx+8], 0
0x18003d594  mov     rcx, [rbx]
0x18003d597  test    rcx, rcx
0x18003d59a  jz      short loc_18003D5A9
0x18003d59c  call    cs:__imp_NsiDisconnectFromServer
0x18003d5a2  mov     qword ptr [rbx], 0
0x18003d5a9  add     rsp, 20h
0x18003d5ad  pop     rbx
0x18003d5ae  retn
```
