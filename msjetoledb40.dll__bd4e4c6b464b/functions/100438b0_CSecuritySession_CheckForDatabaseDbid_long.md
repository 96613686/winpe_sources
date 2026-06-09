# CSecuritySession::CheckForDatabaseDbid(long &)

- ea: `0x100438b0`
- end: `0x100438dc`
- name: `?CheckForDatabaseDbid@CSecuritySession@@QAEJAAJ@Z`
- size: `44`
- prototype: `int __thiscall(CSecuritySession *__hidden this, int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10042630`
- `0x100429a0`
- `0x10042c60`
- `0x10043310`

## callees

- `0x100198d0`
- `0x100438b0`

## pseudocode

```c
int __thiscall CSecuritySession::CheckForDatabaseDbid(CSecuritySession *this, int *a2)
{
  if ( *((_DWORD *)this + 3) == -1 )
    return CDataSource::JETOpenDatabase(
             *((CDataSource **)this + 4),
             (unsigned int *)this + 1,
             (unsigned int *)this + 3,
             (unsigned int *)a2,
             0,
             0);
  else
    return 0;
}

```

## disassembly

```asm
0x100438b0  mov     edi, edi
0x100438b2  push    ebp
0x100438b3  mov     ebp, esp
0x100438b5  cmp     dword ptr [ecx+0Ch], 0FFFFFFFFh
0x100438b9  lea     eax, [ecx+0Ch]
0x100438bc  jnz     short loc_100438D6
0x100438be  push    0; unsigned int *
0x100438c0  push    0; unsigned __int16 *
0x100438c2  push    [ebp+arg_0]; int *
0x100438c5  push    eax; unsigned int *
0x100438c6  lea     eax, [ecx+4]
0x100438c9  mov     ecx, [ecx+10h]; this
0x100438cc  push    eax; unsigned int *
0x100438cd  call    ?JETOpenDatabase@CDataSource@@QAEJAAK0AAJPAGPAK@Z; CDataSource::JETOpenDatabase(ulong &,ulong &,long &,ushort *,ulong *)
0x100438d2  pop     ebp
0x100438d3  retn    4
0x100438d6  xor     eax, eax
0x100438d8  pop     ebp
0x100438d9  retn    4
```
