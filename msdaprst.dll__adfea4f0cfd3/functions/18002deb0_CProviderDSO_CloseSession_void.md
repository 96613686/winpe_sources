# CProviderDSO::CloseSession(void)

- ea: `0x18002deb0`
- end: `0x18002df24`
- name: `?CloseSession@CProviderDSO@@UEAAXXZ`
- size: `116`
- prototype: `void __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002deb0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002ded8`
- `KERNEL32!GetCurrentThreadId` at `0x18002ded8`
- `KERNEL32!LeaveCriticalSection` at `0x18002df18`
- `MSDART!UMSEnterCSWraper` at `0x18002dec6`
- `MSDART!UMSEnterCSWraper` at `0x18002dec6`

## pseudocode

```c
void __fastcall CProviderDSO::CloseSession(CProviderDSO *this)
{
  __int64 v3; // rcx

  UMSEnterCSWraper((char *)this + 72);
  if ( !*((_DWORD *)this + 21) )
    *((_DWORD *)this + 20) = GetCurrentThreadId();
  ++*((_DWORD *)this + 21);
  ++*((_DWORD *)this + 22);
  --*((_DWORD *)this + 16);
  --*((_DWORD *)this + 22);
  if ( (*((_DWORD *)this + 21))-- == 1 )
    *((_DWORD *)this + 20) = -1;
  v3 = *((_QWORD *)this + 9);
  --*(_DWORD *)(v3 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
}

```

## disassembly

```asm
0x18002deb0  mov     [rsp+arg_8], rbx
0x18002deb5  mov     [rsp+arg_10], rsi
0x18002deba  push    rdi
0x18002debb  sub     rsp, 20h
0x18002debf  mov     rsi, rcx
0x18002dec2  add     rcx, 48h ; 'H'
0x18002dec6  call    cs:__imp_UMSEnterCSWraper
0x18002decd  nop     dword ptr [rax+rax+00h]
0x18002ded2  cmp     dword ptr [rsi+54h], 0
0x18002ded6  jnz     short loc_18002DEE7
0x18002ded8  call    cs:__imp_GetCurrentThreadId
0x18002dedf  nop     dword ptr [rax+rax+00h]
0x18002dee4  mov     [rsi+50h], eax
0x18002dee7  inc     dword ptr [rsi+54h]
0x18002deea  or      ecx, 0FFFFFFFFh
0x18002deed  inc     dword ptr [rsi+58h]
0x18002def0  add     [rsi+40h], ecx
0x18002def3  add     [rsi+58h], ecx
0x18002def6  add     [rsi+54h], ecx
0x18002def9  jnz     short loc_18002DEFE
0x18002defb  mov     [rsi+50h], ecx
0x18002defe  mov     rcx, [rsi+48h]
0x18002df02  dec     dword ptr [rcx+30h]
0x18002df05  add     rcx, 8
0x18002df09  mov     rbx, [rsp+28h+arg_8]
0x18002df0e  mov     rsi, [rsp+28h+arg_10]
0x18002df13  add     rsp, 20h
0x18002df17  pop     rdi
0x18002df18  jmp     cs:__imp_LeaveCriticalSection
```
