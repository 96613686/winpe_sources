# DfdManager::CheckDFDRegistry(HKEY__ *)

- ea: `0x180006020`
- end: `0x1800061ec`
- name: `?CheckDFDRegistry@DfdManager@@QEAAHPEAUHKEY__@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(DfdManager *__hidden this, HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002ed8`

## callees

- `0x180002c90`
- `0x180003924`
- `0x180006020`
- `0x1800061f4`
- `0x18000833b`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006057`
- `KERNEL32!HeapAlloc` at `0x180006057`
- `KERNEL32!GetProcessHeap` at `0x180006045`
- `KERNEL32!GetProcessHeap` at `0x1800061bf`
- `KERNEL32!GetProcessHeap` at `0x180006045`
- `KERNEL32!GetProcessHeap` at `0x1800061bf`
- `KERNEL32!HeapFree` at `0x1800061cd`
- `KERNEL32!HeapFree` at `0x1800061cd`
- `ADVAPI32!RegEnumKeyExW` at `0x1800060fe`
- `ADVAPI32!RegEnumKeyExW` at `0x1800060fe`

## pseudocode

```c
__int64 __fastcall DfdManager::CheckDFDRegistry(DfdManager *this, HKEY hKey)
{
  unsigned int v2; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rsi
  unsigned int v7; // ebx
  DWORD v8; // r15d
  unsigned int v9; // eax
  unsigned int v10; // eax
  HANDLE v11; // rax
  int v13; // [rsp+80h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+20h] BYREF

  v2 = 0;
  v13 = 0;
  cchName = 0;
  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x100u);
  if ( v6 )
  {
    v7 = 0;
    v8 = 0;
    while ( !v7 || v7 == 234 )
    {
      cchName = 128;
      v9 = RegEnumKeyExW(hKey, v8, v6, &cchName, 0, 0, 0, 0);
      v7 = v9;
      if ( v9 != 234 && v9 )
      {
        if ( v9 == 259 )
        {
          v7 = 0;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v9);
        }
        break;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v6);
      if ( !v7 )
      {
        v10 = DfdManager::CheckGuid(this, v6, &v13);
        v2 = v13;
        v7 = v10;
        if ( !v10 )
        {
          if ( v13 )
          {
            *((_QWORD *)this + 3) = v6;
            break;
          }
        }
      }
      ++v8;
      memset_0(v6, 0, 0x100u);
    }
    if ( !v2 || v7 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, 14);
  }
  return v2;
}

```

## disassembly

```asm
0x180006020  mov     rax, rsp
0x180006023  mov     [rax+8], rbx
0x180006027  mov     [rax+10h], rbp
0x18000602b  push    rsi
0x18000602c  push    rdi
0x18000602d  push    r12
0x18000602f  push    r14
0x180006031  push    r15
0x180006033  sub     rsp, 40h
0x180006037  xor     edi, edi
0x180006039  mov     r12, rdx
0x18000603c  mov     [rax+18h], edi
0x18000603f  mov     r14, rcx
0x180006042  mov     [rax+20h], edi
0x180006045  call    cs:__imp_GetProcessHeap
0x18000604b  lea     edx, [rdi+8]; dwFlags
0x18000604e  mov     r8d, 100h; dwBytes
0x180006054  mov     rcx, rax; hHeap
0x180006057  call    cs:__imp_HeapAlloc
0x18000605d  mov     rsi, rax
0x180006060  test    rax, rax
0x180006063  jnz     short loc_1800060A2
0x180006065  mov     rcx, cs:WPP_GLOBAL_Control
0x18000606c  lea     rbp, WPP_GLOBAL_Control
0x180006073  cmp     rcx, rbp
0x180006076  jz      loc_1800061D3
0x18000607c  test    byte ptr [rcx+1Ch], 1
0x180006080  jz      loc_1800061D3
0x180006086  mov     rcx, [rcx+10h]
0x18000608a  lea     edx, [rdi+15h]
0x18000608d  lea     r9d, [rdi+0Eh]
0x180006091  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006098  call    WPP_SF_d
0x18000609d  jmp     loc_1800061D3
0x1800060a2  xor     ebx, ebx
0x1800060a4  lea     rbp, WPP_GLOBAL_Control
0x1800060ab  xor     r15d, r15d
0x1800060ae  test    ebx, ebx
0x1800060b0  jz      short loc_1800060BE
0x1800060b2  cmp     ebx, 0EAh
0x1800060b8  jnz     loc_1800061B7
0x1800060be  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800060c7  lea     r9, [rsp+68h+cchName]; lpcchName
0x1800060cf  mov     [rsp+68h+lpcchClass], 0; lpcchClass
0x1800060d8  mov     r8, rsi; lpName
0x1800060db  mov     [rsp+68h+lpClass], 0; lpClass
0x1800060e4  mov     edx, r15d; dwIndex
0x1800060e7  mov     rcx, r12; hKey
0x1800060ea  mov     [rsp+68h+lpReserved], 0; lpReserved
0x1800060f3  mov     [rsp+68h+cchName], 80h
0x1800060fe  call    cs:__imp_RegEnumKeyExW
0x180006104  mov     ebx, eax
0x180006106  cmp     eax, 0EAh
0x18000610b  jz      short loc_180006111
0x18000610d  test    eax, eax
0x18000610f  jnz     short loc_18000617B
0x180006111  mov     rcx, cs:WPP_GLOBAL_Control
0x180006118  cmp     rcx, rbp
0x18000611b  jz      short loc_18000613B
0x18000611d  test    byte ptr [rcx+1Ch], 4
0x180006121  jz      short loc_18000613B
0x180006123  mov     rcx, [rcx+10h]
0x180006127  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x18000612e  mov     edx, 17h
0x180006133  mov     r9, rsi
0x180006136  call    WPP_SF_S
0x18000613b  test    ebx, ebx
0x18000613d  jnz     short loc_180006163
0x18000613f  lea     r8, [rsp+68h+arg_10]; int *
0x180006147  mov     rdx, rsi; unsigned __int16 *
0x18000614a  mov     rcx, r14; this
0x18000614d  call    ?CheckGuid@DfdManager@@AEAAJPEAGPEAH@Z; DfdManager::CheckGuid(ushort *,int *)
0x180006152  mov     edi, [rsp+68h+arg_10]
0x180006159  mov     ebx, eax
0x18000615b  test    eax, eax
0x18000615d  jnz     short loc_180006163
0x18000615f  test    edi, edi
0x180006161  jnz     short loc_1800061B3
0x180006163  inc     r15d
0x180006166  xor     edx, edx; Val
0x180006168  mov     r8d, 100h; Size
0x18000616e  mov     rcx, rsi; void *
0x180006171  call    memset_0
0x180006176  jmp     loc_1800060AE
0x18000617b  cmp     ebx, 103h
0x180006181  jnz     short loc_180006187
0x180006183  xor     ebx, ebx
0x180006185  jmp     short loc_1800061B7
0x180006187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000618e  cmp     rcx, rbp
0x180006191  jz      short loc_1800061B7
0x180006193  test    byte ptr [rcx+1Ch], 1
0x180006197  jz      short loc_1800061B7
0x180006199  mov     rcx, [rcx+10h]
0x18000619d  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x1800061a4  mov     edx, 16h
0x1800061a9  mov     r9d, ebx
0x1800061ac  call    WPP_SF_d
0x1800061b1  jmp     short loc_1800061B7
0x1800061b3  mov     [r14+18h], rsi
0x1800061b7  test    edi, edi
0x1800061b9  jz      short loc_1800061BF
0x1800061bb  test    ebx, ebx
0x1800061bd  jz      short loc_1800061D3
0x1800061bf  call    cs:__imp_GetProcessHeap
0x1800061c5  mov     r8, rsi; lpMem
0x1800061c8  xor     edx, edx; dwFlags
0x1800061ca  mov     rcx, rax; hHeap
0x1800061cd  call    cs:__imp_HeapFree
0x1800061d3  mov     rbx, [rsp+68h+arg_0]
0x1800061d8  mov     eax, edi
0x1800061da  mov     rbp, [rsp+68h+arg_8]
0x1800061df  add     rsp, 40h
0x1800061e3  pop     r15
0x1800061e5  pop     r14
0x1800061e7  pop     r12
0x1800061e9  pop     rdi
0x1800061ea  pop     rsi
0x1800061eb  retn
```
