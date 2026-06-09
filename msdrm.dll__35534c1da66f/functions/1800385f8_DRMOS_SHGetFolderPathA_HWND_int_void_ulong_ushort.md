# DRMOS::SHGetFolderPathA(HWND__ *,int,void *,ulong,ushort *)

- ea: `0x1800385f8`
- end: `0x1800386e7`
- name: `?SHGetFolderPathA@DRMOS@@YAJPEAUHWND__@@HPEAXKPEAG@Z`
- size: `239`
- prototype: `__int64 __fastcall(DRMOS *__hidden this, HWND, int, void *, LPWSTR, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037fa8`

## callees

- `0x1800385f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386cf`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003863f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003863f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800386ac`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1800386ac`

## pseudocode

```c
__int64 __fastcall DRMOS::SHGetFolderPathA(DRMOS *this, HWND a2, __int64 a3, void *a4, LPWSTR pszPath)
{
  LPWSTR v5; // rdi
  HRESULT v6; // ebx
  PWSTR v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  LPWSTR v10; // rcx
  PWSTR ppszPath; // [rsp+50h] [rbp+18h] BYREF

  v5 = pszPath;
  ppszPath = 0;
  if ( pszPath )
  {
    if ( (_DWORD)a2 == 28 )
    {
      v6 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x4000u, 0, &ppszPath);
      if ( v6 >= 0 )
      {
        v7 = ppszPath;
        v8 = 2147483646;
        v9 = 260;
        do
        {
          if ( !v8 )
            break;
          if ( !*v7 )
            break;
          *v5++ = *v7++;
          --v8;
          --v9;
        }
        while ( v9 );
        v10 = v5 - 1;
        if ( v9 )
          v10 = v5;
        v6 = v9 == 0 ? 0x8007007A : 0;
        *v10 = 0;
      }
    }
    else
    {
      v6 = SHGetFolderPathW(0, (unsigned int)a2 | 0x8000, 0, 0, pszPath);
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( GetLastError() == 14 )
    v6 = -2147024882;
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800385f8  mov     rax, rsp
0x1800385fb  mov     [rax+8], rbx
0x1800385ff  mov     [rax+10h], rsi
0x180038603  mov     [rax+18h], r8
0x180038607  push    rdi
0x180038608  sub     rsp, 30h
0x18003860c  mov     rdi, [rsp+38h+arg_20]
0x180038611  xor     esi, esi
0x180038613  mov     [rax+18h], rsi
0x180038617  test    rdi, rdi
0x18003861a  jnz     short loc_180038626
0x18003861c  mov     ebx, 80070057h
0x180038621  jmp     loc_1800386B4
0x180038626  xor     r8d, r8d; hToken
0x180038629  cmp     edx, 1Ch
0x18003862c  jnz     short loc_18003869E
0x18003862e  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x180038633  mov     edx, 4000h; dwFlags
0x180038638  lea     rcx, FOLDERID_LocalAppData; rfid
0x18003863f  call    cs:__imp_SHGetKnownFolderPath
0x180038645  mov     ebx, eax
0x180038647  test    eax, eax
0x180038649  js      short loc_1800386B4
0x18003864b  mov     rcx, [rsp+38h+ppszPath]
0x180038650  mov     eax, 7FFFFFFEh
0x180038655  mov     edx, 104h
0x18003865a  test    rax, rax
0x18003865d  jz      short loc_18003867E
0x18003865f  movzx   r8d, word ptr [rcx]
0x180038663  test    r8w, r8w
0x180038667  jz      short loc_18003867E
0x180038669  mov     [rdi], r8w
0x18003866d  add     rcx, 2
0x180038671  add     rdi, 2
0x180038675  dec     rax
0x180038678  sub     rdx, 1
0x18003867c  jnz     short loc_18003865A
0x18003867e  test    rdx, rdx
0x180038681  lea     rcx, [rdi-2]
0x180038685  mov     rax, rdx
0x180038688  cmovnz  rcx, rdi
0x18003868c  neg     rax
0x18003868f  sbb     ebx, ebx
0x180038691  not     ebx
0x180038693  and     ebx, 8007007Ah
0x180038699  mov     [rcx], si
0x18003869c  jmp     short loc_1800386B4
0x18003869e  bts     edx, 0Fh; csidl
0x1800386a2  mov     [rsp+38h+pszPath], rdi; pszPath
0x1800386a7  xor     r9d, r9d; dwFlags
0x1800386aa  xor     ecx, ecx; hwnd
0x1800386ac  call    cs:__imp_SHGetFolderPathW
0x1800386b2  mov     ebx, eax
0x1800386b4  call    cs:__imp_GetLastError
0x1800386ba  cmp     eax, 0Eh
0x1800386bd  mov     ecx, 8007000Eh
0x1800386c2  cmovz   ebx, ecx
0x1800386c5  mov     rcx, [rsp+38h+ppszPath]; pv
0x1800386ca  test    rcx, rcx
0x1800386cd  jz      short loc_1800386D5
0x1800386cf  call    cs:__imp_CoTaskMemFree
0x1800386d5  mov     rsi, [rsp+38h+arg_8]
0x1800386da  mov     eax, ebx
0x1800386dc  mov     rbx, [rsp+38h+arg_0]
0x1800386e1  add     rsp, 30h
0x1800386e5  pop     rdi
0x1800386e6  retn
```
