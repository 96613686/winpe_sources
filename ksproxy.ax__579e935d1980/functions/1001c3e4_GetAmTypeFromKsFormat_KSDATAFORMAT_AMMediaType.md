# GetAmTypeFromKsFormat(KSDATAFORMAT *,_AMMediaType * *)

- ea: `0x1001c3e4`
- end: `0x1001c488`
- name: `?GetAmTypeFromKsFormat@@YGJPATKSDATAFORMAT@@PAPAU_AMMediaType@@@Z`
- size: `164`
- prototype: `int __stdcall(union KSDATAFORMAT *, struct _AMMediaType **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1001c490`

## callees

- `0x1001c3e4`
- `0x10030181`
- `0x1003035c`
- `0x1003b5e4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001c3fc`
- `ole32!CoTaskMemAlloc` at `0x1001c3fc`

## pseudocode

```c
int __fastcall GetAmTypeFromKsFormat(int a1, int *a2)
{
  void *v2; // eax
  int v3; // ebx
  int v7; // [esp+Ch] [ebp-4h]

  v7 = 0;
  v2 = CoTaskMemAlloc(0x48u);
  v3 = (int)v2;
  if ( !v2 )
    goto LABEL_4;
  memset(v2, 0, 0x48u);
  *(_DWORD *)v3 = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(v3 + 4) = *(_DWORD *)(a1 + 20);
  *(_DWORD *)(v3 + 8) = *(_DWORD *)(a1 + 24);
  *(_DWORD *)(v3 + 12) = *(_DWORD *)(a1 + 28);
  *(_DWORD *)(v3 + 16) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(v3 + 20) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(v3 + 24) = *(_DWORD *)(a1 + 40);
  *(_DWORD *)(v3 + 28) = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(v3 + 44) = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(v3 + 48) = *(_DWORD *)(a1 + 52);
  *(_DWORD *)(v3 + 52) = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(v3 + 56) = *(_DWORD *)(a1 + 60);
  *(_DWORD *)(v3 + 32) = *(_DWORD *)(a1 + 8) != 0;
  *(_DWORD *)(v3 + 36) = *(_DWORD *)(a1 + 4) & 1;
  *(_DWORD *)(v3 + 40) = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)a1 <= 0x40u
    || CMediaType::SetFormat((CMediaType *)v3, (unsigned __int8 *)(a1 + 64), *(_DWORD *)a1 - 64) )
  {
    *a2 = v3;
  }
  else
  {
LABEL_4:
    v7 = -2147467259;
    FreeMediaType(v3);
  }
  return v7;
}

```

## disassembly

```asm
0x1001c3e4  mov     edi, edi
0x1001c3e6  push    ebp
0x1001c3e7  mov     ebp, esp
0x1001c3e9  sub     esp, 0Ch
0x1001c3ec  push    ebx; struct _AMMediaType *
0x1001c3ed  push    48h ; 'H'; cb
0x1001c3ef  mov     [ebp+var_C], edx
0x1001c3f2  mov     [ebp+var_8], ecx
0x1001c3f5  mov     [ebp+var_4], 0
0x1001c3fc  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001c402  mov     ebx, eax
0x1001c404  test    ebx, ebx
0x1001c406  jz      short loc_1001C46D
0x1001c408  push    esi
0x1001c409  push    edi
0x1001c40a  push    48h ; 'H'; Size
0x1001c40c  push    0; Val
0x1001c40e  push    ebx; void *
0x1001c40f  call    _memset
0x1001c414  mov     ecx, [ebp+var_8]
0x1001c417  mov     edi, ebx
0x1001c419  xor     eax, eax
0x1001c41b  add     esp, 0Ch
0x1001c41e  lea     esi, [ecx+10h]
0x1001c421  movsd
0x1001c422  movsd
0x1001c423  movsd
0x1001c424  movsd
0x1001c425  lea     esi, [ecx+20h]
0x1001c428  lea     edi, [ebx+10h]
0x1001c42b  movsd
0x1001c42c  movsd
0x1001c42d  movsd
0x1001c42e  movsd
0x1001c42f  lea     esi, [ecx+30h]
0x1001c432  lea     edi, [ebx+2Ch]
0x1001c435  movsd
0x1001c436  movsd
0x1001c437  movsd
0x1001c438  movsd
0x1001c439  cmp     [ecx+8], eax
0x1001c43c  pop     edi
0x1001c43d  setnz   al
0x1001c440  mov     [ebx+20h], eax
0x1001c443  mov     eax, [ecx+4]
0x1001c446  and     eax, 1
0x1001c449  mov     [ebx+24h], eax
0x1001c44c  mov     eax, [ecx+8]
0x1001c44f  mov     [ebx+28h], eax
0x1001c452  mov     eax, [ecx]
0x1001c454  pop     esi
0x1001c455  cmp     eax, 40h ; '@'
0x1001c458  jbe     short loc_1001C47D
0x1001c45a  add     eax, 0FFFFFFC0h
0x1001c45d  push    eax; unsigned int
0x1001c45e  lea     eax, [ecx+40h]
0x1001c461  mov     ecx, ebx; this
0x1001c463  push    eax; Src
0x1001c464  call    ?SetFormat@CMediaType@@QAEHPAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x1001c469  test    eax, eax
0x1001c46b  jnz     short loc_1001C47D
0x1001c46d  mov     ecx, ebx
0x1001c46f  mov     [ebp+var_4], 80004005h
0x1001c476  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1001c47b  jmp     short loc_1001C482
0x1001c47d  mov     eax, [ebp+var_C]
0x1001c480  mov     [eax], ebx
0x1001c482  mov     eax, [ebp+var_4]
0x1001c485  pop     ebx
0x1001c486  leave
0x1001c487  retn
```
