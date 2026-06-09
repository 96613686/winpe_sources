# CACHED_FILE_INFO::GetHttpCacheAllowed(ulong *)

- ea: `0x1800025d0`
- end: `0x18000264a`
- name: `?GetHttpCacheAllowed@CACHED_FILE_INFO@@UEBAHPEAK@Z`
- size: `122`
- prototype: `__int64 __fastcall(CACHED_FILE_INFO *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800025d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002626`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002626`

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::GetHttpCacheAllowed(CACHED_FILE_INFO *this, unsigned int *a2)
{
  unsigned int v3; // edx
  DWORD v5; // edi
  int v6; // ebx
  DWORD v7; // ecx

  if ( !*((_BYTE *)g_pFileCache + 65) )
    return 0;
  if ( *((_QWORD *)this + 41) )
  {
    v3 = -1;
  }
  else
  {
    v5 = *((_DWORD *)g_pFileCache + 17);
    v6 = *((_DWORD *)this + 85);
    v7 = v5 + v6 - GetTickCount();
    if ( v7 <= v5 )
      v3 = v7 / 0x3E8;
    else
      v3 = 0;
  }
  *a2 = v3;
  return 1;
}

```

## disassembly

```asm
0x1800025d0  mov     [rsp+arg_8], rsi
0x1800025d5  push    rdi
0x1800025d6  sub     rsp, 20h
0x1800025da  mov     rdi, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800025e1  mov     rsi, rdx
0x1800025e4  cmp     byte ptr [rdi+41h], 0
0x1800025e8  jz      short loc_18000260B
0x1800025ea  cmp     qword ptr [rcx+148h], 0
0x1800025f2  jz      short loc_180002618
0x1800025f4  mov     edx, 0FFFFFFFFh
0x1800025f9  mov     [rsi], edx
0x1800025fb  mov     eax, 1
0x180002600  mov     rsi, [rsp+28h+arg_8]
0x180002605  add     rsp, 20h
0x180002609  pop     rdi
0x18000260a  retn
0x18000260b  mov     rsi, [rsp+28h+arg_8]
0x180002610  xor     eax, eax
0x180002612  add     rsp, 20h
0x180002616  pop     rdi
0x180002617  retn
0x180002618  mov     edi, [rdi+44h]
0x18000261b  mov     [rsp+28h+arg_0], rbx
0x180002620  mov     ebx, [rcx+154h]
0x180002626  call    cs:__imp_GetTickCount
0x18000262c  lea     ecx, [rdi+rbx]
0x18000262f  mov     rbx, [rsp+28h+arg_0]
0x180002634  sub     ecx, eax
0x180002636  cmp     ecx, edi
0x180002638  jbe     short loc_18000263E
0x18000263a  xor     edx, edx
0x18000263c  jmp     short loc_1800025F9
0x18000263e  mov     eax, 10624DD3h
0x180002643  mul     ecx
0x180002645  shr     edx, 6
0x180002648  jmp     short loc_1800025F9
```
