# PersistRegStore::InternalDeleteObject(PersistObject *)

- ea: `0x180028920`
- end: `0x1800289d3`
- name: `?InternalDeleteObject@PersistRegStore@@MEAAJPEAVPersistObject@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(HKEY *this, struct PersistObject *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180028920`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002897d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002897d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002898a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002898a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800289a3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800289a3`

## pseudocode

```c
__int64 __fastcall PersistRegStore::InternalDeleteObject(HKEY *this, struct PersistObject *a2)
{
  HKEY v2; // rax
  int v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  const WCHAR *v7; // rbp
  LSTATUS v8; // eax
  int v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *this;
  v10 = 0;
  if ( (*((unsigned int (__fastcall **)(HKEY *))v2 + 9))(this) )
  {
    v5 = (*((__int64 (__fastcall **)(HKEY *, int *))*this + 1))(this, &v10);
    if ( v5 >= 0 )
    {
      if ( v10 )
      {
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 32);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
        v7 = (const WCHAR *)*((_QWORD *)a2 + 3);
        LeaveCriticalSection(v6);
        if ( v7 )
        {
          v8 = RegDeleteKeyW(this[2], v7);
          if ( v8 == 2 )
          {
            return (unsigned int)-2147023728;
          }
          else if ( v8 )
          {
            if ( v8 > 0 )
              return (unsigned __int16)v8 | 0x80070000;
            else
              return (unsigned int)v8;
          }
        }
        else
        {
          return (unsigned int)-2147024809;
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  else
  {
    return (unsigned int)-2102788096;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028920  push    rbx
0x180028922  push    rbp
0x180028923  push    rsi
0x180028924  push    rdi
0x180028925  sub     rsp, 28h
0x180028929  mov     rax, [rcx]
0x18002892c  mov     rbp, rdx
0x18002892f  mov     rsi, rcx
0x180028932  mov     [rsp+48h+arg_0], 0
0x18002893a  mov     rax, [rax+48h]
0x18002893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028943  test    eax, eax
0x180028945  jnz     short loc_18002894E
0x180028947  mov     edi, 82AA0000h
0x18002894c  jmp     short loc_1800289C8
0x18002894e  mov     rax, [rsi]
0x180028951  lea     rdx, [rsp+48h+arg_0]
0x180028956  mov     rcx, rsi
0x180028959  mov     rax, [rax+8]
0x18002895d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028962  mov     edi, eax
0x180028964  test    eax, eax
0x180028966  js      short loc_1800289C8
0x180028968  cmp     [rsp+48h+arg_0], 0
0x18002896d  jnz     short loc_180028976
0x18002896f  mov     edi, 8000FFFFh
0x180028974  jmp     short loc_1800289C8
0x180028976  lea     rbx, [rbp+20h]
0x18002897a  mov     rcx, rbx; lpCriticalSection
0x18002897d  call    cs:__imp_EnterCriticalSection
0x180028983  mov     rbp, [rbp+18h]
0x180028987  mov     rcx, rbx; lpCriticalSection
0x18002898a  call    cs:__imp_LeaveCriticalSection
0x180028990  test    rbp, rbp
0x180028993  jnz     short loc_18002899C
0x180028995  mov     edi, 80070057h
0x18002899a  jmp     short loc_1800289C8
0x18002899c  mov     rcx, [rsi+10h]; hKey
0x1800289a0  mov     rdx, rbp; lpSubKey
0x1800289a3  call    cs:__imp_RegDeleteKeyW
0x1800289a9  cmp     eax, 2
0x1800289ac  jnz     short loc_1800289B5
0x1800289ae  mov     edi, 80070490h
0x1800289b3  jmp     short loc_1800289C8
0x1800289b5  test    eax, eax
0x1800289b7  jz      short loc_1800289C8
0x1800289b9  jg      short loc_1800289BF
0x1800289bb  mov     edi, eax
0x1800289bd  jmp     short loc_1800289C8
0x1800289bf  movzx   edi, ax
0x1800289c2  or      edi, 80070000h
0x1800289c8  mov     eax, edi
0x1800289ca  add     rsp, 28h
0x1800289ce  pop     rdi
0x1800289cf  pop     rsi
0x1800289d0  pop     rbp
0x1800289d1  pop     rbx
0x1800289d2  retn
```
