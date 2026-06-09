# PROTOCOL::ReceiveCompletion(long,ulong)

- ea: `0x180003910`
- end: `0x180003993`
- name: `?ReceiveCompletion@PROTOCOL@@UEAAXJK@Z`
- size: `131`
- prototype: `void __fastcall(PROTOCOL *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800033e0`
- `0x1800036b8`
- `0x180003910`
- `0x180006480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003957`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003938`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003938`

## pseudocode

```c
void __fastcall PROTOCOL::ReceiveCompletion(PROTOCOL *this, int a2, int a3)
{
  int v6; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 27) )
  {
    v6 = -2147023901;
  }
  else
  {
    *((_DWORD *)this + 48) = GetTickCount();
    v6 = PROTOCOL::RealReceiveCompletion((struct FCGI_BUFFER **)this, a2, a3);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v6 < 0 && !*((_DWORD *)this + 27) )
    APPLICATION::RealShutdown(*((APPLICATION **)this + 21), v6, 0, 0, 1);
  PROTOCOL::DereferenceProtocol(this);
}

```

## disassembly

```asm
0x180003910  push    rbx
0x180003912  push    rbp
0x180003913  push    rsi
0x180003914  push    rdi
0x180003915  sub     rsp, 38h
0x180003919  mov     rbx, rcx
0x18000391c  mov     edi, r8d
0x18000391f  add     rcx, 40h ; '@'; lpCriticalSection
0x180003923  mov     ebp, edx
0x180003925  call    cs:__imp_EnterCriticalSection
0x18000392b  cmp     dword ptr [rbx+6Ch], 0
0x18000392f  jz      short loc_180003938
0x180003931  mov     edi, 800703E3h
0x180003936  jmp     short loc_180003953
0x180003938  call    cs:__imp_GetTickCount
0x18000393e  mov     r8d, edi; unsigned int
0x180003941  mov     edx, ebp; unsigned int
0x180003943  mov     rcx, rbx; this
0x180003946  mov     [rbx+0C0h], eax
0x18000394c  call    ?RealReceiveCompletion@PROTOCOL@@AEAAJKK@Z; PROTOCOL::RealReceiveCompletion(ulong,ulong)
0x180003951  mov     edi, eax
0x180003953  lea     rcx, [rbx+40h]; lpCriticalSection
0x180003957  call    cs:__imp_LeaveCriticalSection
0x18000395d  test    edi, edi
0x18000395f  jns     short loc_180003983
0x180003961  cmp     dword ptr [rbx+6Ch], 0
0x180003965  jnz     short loc_180003983
0x180003967  mov     rcx, [rbx+0A8h]; this
0x18000396e  xor     r9d, r9d; int
0x180003971  xor     r8d, r8d; unsigned int
0x180003974  mov     [rsp+58h+var_38], 1; int
0x18000397c  mov     edx, edi; int
0x18000397e  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x180003983  mov     rcx, rbx; this
0x180003986  add     rsp, 38h
0x18000398a  pop     rdi
0x18000398b  pop     rsi
0x18000398c  pop     rbp
0x18000398d  pop     rbx
0x18000398e  jmp     ?DereferenceProtocol@PROTOCOL@@QEAAXXZ; PROTOCOL::DereferenceProtocol(void)
```
