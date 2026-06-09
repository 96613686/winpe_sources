# FREB_TIMEOUT_MONITOR_LIST::DoExpirationCheck(void *,uchar)

- ea: `0x180005800`
- end: `0x180005944`
- name: `?DoExpirationCheck@FREB_TIMEOUT_MONITOR_LIST@@SAXPEAXE@Z`
- size: `324`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005800`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005832`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005832`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005910`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005910`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000588c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000588c`

## pseudocode

```c
void __fastcall FREB_TIMEOUT_MONITOR_LIST::DoExpirationCheck(char *a1)
{
  DWORD TickCount; // kr00_4
  int v3; // ecx
  unsigned int i; // esi
  __int64 v5; // rax
  char **v6; // rcx
  char *v7; // rdi
  char *v8; // rcx
  int v9; // eax
  char *v10; // rax
  char **v11; // rcx
  int v12; // ecx

  if ( _InterlockedIncrement((volatile signed __int32 *)a1 + 1801) == 1 )
  {
    TickCount = GetTickCount();
    v3 = *((_DWORD *)a1 + 1800);
    for ( i = TickCount / 0x3E8 % 0x12C; v3 != i; v3 = *((_DWORD *)a1 + 1800) )
    {
      v5 = (v3 + 1) % 0x12Cu;
      *((_DWORD *)a1 + 1800) = v5;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&a1[8 * v5 + 4800]);
      v6 = (char **)&a1[16 * *((unsigned int *)a1 + 1800)];
      v7 = *v6;
      if ( *v6 == (char *)v6 )
      {
        v12 = *((_DWORD *)a1 + 1800);
      }
      else
      {
        do
        {
          v8 = v7 - 8;
          v9 = *((_DWORD *)v7 + 4);
          if ( v9 )
          {
            *((_DWORD *)v8 + 6) = v9 - 1;
            v7 = *(char **)v7;
          }
          else
          {
            (**(void (__fastcall ***)(char *))v8)(v8);
            v10 = *(char **)v7;
            if ( *(char **)(*(_QWORD *)v7 + 8LL) != v7 || (v11 = (char **)*((_QWORD *)v7 + 1), *v11 != v7) )
              __fastfail(3u);
            *v11 = v10;
            *((_QWORD *)v10 + 1) = v11;
            *(_QWORD *)v7 = 0;
            v7 = v10;
          }
          v12 = *((_DWORD *)a1 + 1800);
        }
        while ( v7 != &a1[16 * v12] );
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&a1[8 * v12 + 4800]);
    }
    _InterlockedDecrement((volatile signed __int32 *)a1 + 1801);
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)a1 + 1801);
  }
}

```

## disassembly

```asm
0x180005800  mov     [rsp+arg_0], rbx
0x180005805  mov     [rsp+arg_8], rsi
0x18000580a  push    rdi
0x18000580b  sub     rsp, 20h
0x18000580f  mov     rbx, rcx
0x180005812  mov     eax, 1
0x180005817  lock xadd [rcx+1C24h], eax
0x18000581f  inc     eax
0x180005821  cmp     eax, 1
0x180005824  jz      short loc_180005832
0x180005826  lock dec dword ptr [rcx+1C24h]
0x18000582d  jmp     loc_18000592D
0x180005832  call    cs:__imp_GetTickCount
0x180005838  mov     ecx, eax
0x18000583a  mov     eax, 10624DD3h
0x18000583f  mul     ecx
0x180005841  mov     ecx, [rbx+1C20h]
0x180005847  mov     eax, 1B4E81B5h
0x18000584c  mov     esi, edx
0x18000584e  shr     esi, 6
0x180005851  mul     esi
0x180005853  shr     edx, 5
0x180005856  imul    eax, edx, 12Ch
0x18000585c  sub     esi, eax
0x18000585e  cmp     ecx, esi
0x180005860  jz      loc_180005926
0x180005866  inc     ecx
0x180005868  mov     eax, 1B4E81B5h
0x18000586d  mul     ecx
0x18000586f  shr     edx, 5
0x180005872  imul    eax, edx, 12Ch
0x180005878  sub     ecx, eax
0x18000587a  mov     eax, ecx
0x18000587c  mov     [rbx+1C20h], eax
0x180005882  add     rax, 258h
0x180005888  lea     rcx, [rbx+rax*8]
0x18000588c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180005892  mov     edx, [rbx+1C20h]
0x180005898  mov     ecx, edx
0x18000589a  shl     rcx, 4
0x18000589e  add     rcx, rbx
0x1800058a1  mov     rdi, [rcx]
0x1800058a4  cmp     rdi, rcx
0x1800058a7  jz      short loc_180005902
0x1800058a9  lea     rcx, [rdi-8]
0x1800058ad  mov     eax, [rcx+18h]
0x1800058b0  test    eax, eax
0x1800058b2  jz      short loc_1800058BE
0x1800058b4  dec     eax
0x1800058b6  mov     [rcx+18h], eax
0x1800058b9  mov     rdi, [rdi]
0x1800058bc  jmp     short loc_1800058EC
0x1800058be  mov     rax, [rcx]
0x1800058c1  mov     rax, [rax]
0x1800058c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c9  mov     rax, [rdi]
0x1800058cc  cmp     [rax+8], rdi
0x1800058d0  jnz     short loc_18000593D
0x1800058d2  mov     rcx, [rdi+8]
0x1800058d6  cmp     [rcx], rdi
0x1800058d9  jnz     short loc_18000593D
0x1800058db  mov     [rcx], rax
0x1800058de  mov     [rax+8], rcx
0x1800058e2  mov     qword ptr [rdi], 0
0x1800058e9  mov     rdi, rax
0x1800058ec  mov     ecx, [rbx+1C20h]
0x1800058f2  mov     eax, ecx
0x1800058f4  shl     rax, 4
0x1800058f8  add     rax, rbx
0x1800058fb  cmp     rdi, rax
0x1800058fe  jnz     short loc_1800058A9
0x180005900  jmp     short loc_180005904
0x180005902  mov     ecx, edx
0x180005904  mov     eax, ecx
0x180005906  add     rax, 258h
0x18000590c  lea     rcx, [rbx+rax*8]
0x180005910  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180005916  mov     eax, [rbx+1C20h]
0x18000591c  mov     ecx, eax
0x18000591e  cmp     eax, esi
0x180005920  jnz     loc_180005866
0x180005926  lock dec dword ptr [rbx+1C24h]
0x18000592d  mov     rbx, [rsp+28h+arg_0]
0x180005932  mov     rsi, [rsp+28h+arg_8]
0x180005937  add     rsp, 20h
0x18000593b  pop     rdi
0x18000593c  retn
0x18000593d  mov     ecx, 3
0x180005942  int     29h; Win8: RtlFailFast(ecx)
```
