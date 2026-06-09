# ShortcutSerialization::s_PopulateV1Properties(IShellLinkW * const,_CONSOLE_STATE_INFO *)

- ea: `0x180017c78`
- end: `0x180017e49`
- name: `?s_PopulateV1Properties@ShortcutSerialization@@CAJQEAUIShellLinkW@@PEAU_CONSOLE_STATE_INFO@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(struct IShellLinkW *const, struct _CONSOLE_STATE_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800178fc`

## callees

- `0x180005e60`
- `0x180017c78`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017de4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017de4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e22`

## pseudocode

```c
__int64 __fastcall ShortcutSerialization::s_PopulateV1Properties(
        struct IShellLinkW *const a1,
        struct _CONSOLE_STATE_INFO *a2)
{
  struct IShellLinkWVtbl *lpVtbl; // rax
  int v4; // ebx
  __int16 *v5; // r8
  char *v6; // r11
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  HLOCAL v11; // rcx
  __int64 v13; // [rsp+40h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF
  HLOCAL v15; // [rsp+58h] [rbp+38h] BYREF

  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellLinkW *const, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1,
         &v13);
  if ( v4 >= 0 )
  {
    hMem = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v13 + 32LL))(v13, 2684354562LL, &hMem);
    if ( v4 >= 0 )
    {
      v5 = (__int16 *)hMem;
      *((_WORD *)a2 + 50) = *((_WORD *)hMem + 4);
      *((_WORD *)a2 + 51) = v5[5];
      *(_DWORD *)a2 = *((_DWORD *)v5 + 3);
      *((_DWORD *)a2 + 1) = *((_DWORD *)v5 + 4);
      *((_DWORD *)a2 + 2) = v5[10];
      *((_DWORD *)a2 + 3) = v5[11];
      *((_DWORD *)a2 + 4) = *((_DWORD *)v5 + 8);
      *((_DWORD *)a2 + 5) = *((_DWORD *)v5 + 9);
      *((_DWORD *)a2 + 6) = *((_DWORD *)v5 + 10);
      StringCchCopyW((wchar_t *)a2 + 14, 0x20u, (wchar_t *)v5 + 22);
      v6 = (char *)hMem;
      *((_DWORD *)a2 + 23) = *((_DWORD *)hMem + 27);
      v7 = *((_DWORD *)a2 + 24) ^ (*((_DWORD *)v6 + 28) ^ *((_DWORD *)a2 + 24)) & 1;
      *((_DWORD *)a2 + 24) = v7;
      v8 = v7 ^ ((unsigned __int8)v7 ^ (unsigned __int8)(2 * *((_DWORD *)v6 + 29))) & 2;
      *((_DWORD *)a2 + 24) = v8;
      v9 = v8 ^ ((unsigned __int8)v8 ^ (unsigned __int8)(8 * *((_DWORD *)v6 + 30))) & 8;
      *((_DWORD *)a2 + 24) = v9;
      v10 = v9 ^ ((unsigned __int8)v9 ^ (unsigned __int8)(4 * *((_DWORD *)v6 + 31))) & 4;
      *((_DWORD *)a2 + 24) = v10;
      *((_DWORD *)a2 + 26) = *((_DWORD *)v6 + 32);
      *((_DWORD *)a2 + 27) = *((_DWORD *)v6 + 33);
      *((_DWORD *)a2 + 24) = v10 ^ ((unsigned __int8)v10 ^ (unsigned __int8)(16 * *((_DWORD *)v6 + 34))) & 0x10;
      *((_OWORD *)a2 + 7) = *(_OWORD *)(v6 + 140);
      *((_OWORD *)a2 + 8) = *(_OWORD *)(v6 + 156);
      *((_OWORD *)a2 + 9) = *(_OWORD *)(v6 + 172);
      *((_OWORD *)a2 + 10) = *(_OWORD *)(v6 + 188);
      LocalFree(v6);
      v15 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v13 + 32LL))(v13, 2684354564LL, &v15) >= 0 )
      {
        v11 = v15;
        *((_DWORD *)a2 + 52) = *((_DWORD *)v15 + 2);
        LocalFree(v11);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017c78  push    rbp
0x180017c7a  push    rbx
0x180017c7b  push    rdi
0x180017c7c  mov     rbp, rsp
0x180017c7f  sub     rsp, 20h
0x180017c83  mov     rax, [rcx]
0x180017c86  lea     r8, [rbp+arg_0]
0x180017c8a  mov     rdi, rdx
0x180017c8d  mov     [rbp+arg_0], 0
0x180017c95  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x180017c9c  mov     rax, [rax]
0x180017c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca4  mov     ebx, eax
0x180017ca6  test    eax, eax
0x180017ca8  js      loc_180017E3E
0x180017cae  mov     rcx, [rbp+arg_0]
0x180017cb2  lea     r8, [rbp+hMem]
0x180017cb6  mov     [rbp+hMem], 0
0x180017cbe  mov     edx, 0A0000002h
0x180017cc3  mov     rax, [rcx]
0x180017cc6  mov     rax, [rax+20h]
0x180017cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ccf  mov     ebx, eax
0x180017cd1  test    eax, eax
0x180017cd3  js      loc_180017E2E
0x180017cd9  mov     r8, [rbp+hMem]
0x180017cdd  lea     rcx, [rdi+1Ch]; wchar_t *
0x180017ce1  mov     edx, 20h ; ' '; unsigned __int64
0x180017ce6  movzx   eax, word ptr [r8+8]
0x180017ceb  mov     [rdi+64h], ax
0x180017cef  movzx   eax, word ptr [r8+0Ah]
0x180017cf4  mov     [rdi+66h], ax
0x180017cf8  mov     eax, [r8+0Ch]
0x180017cfc  mov     [rdi], eax
0x180017cfe  mov     eax, [r8+10h]
0x180017d02  mov     [rdi+4], eax
0x180017d05  movsx   eax, word ptr [r8+14h]
0x180017d0a  mov     [rdi+8], eax
0x180017d0d  movsx   eax, word ptr [r8+16h]
0x180017d12  mov     [rdi+0Ch], eax
0x180017d15  mov     eax, [r8+20h]
0x180017d19  mov     [rdi+10h], eax
0x180017d1c  mov     eax, [r8+24h]
0x180017d20  mov     [rdi+14h], eax
0x180017d23  mov     eax, [r8+28h]
0x180017d27  add     r8, 2Ch ; ','; wchar_t *
0x180017d2b  mov     [rdi+18h], eax
0x180017d2e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180017d33  mov     r11, [rbp+hMem]
0x180017d37  mov     eax, [r11+6Ch]
0x180017d3b  mov     [rdi+5Ch], eax
0x180017d3e  mov     eax, [rdi+60h]
0x180017d41  xor     eax, [r11+70h]
0x180017d45  and     eax, 1
0x180017d48  xor     eax, [rdi+60h]
0x180017d4b  mov     [rdi+60h], eax
0x180017d4e  mov     ecx, [r11+74h]
0x180017d52  add     ecx, ecx
0x180017d54  xor     ecx, eax
0x180017d56  and     ecx, 2
0x180017d59  xor     ecx, eax
0x180017d5b  mov     [rdi+60h], ecx
0x180017d5e  mov     eax, [r11+78h]
0x180017d62  shl     eax, 3
0x180017d65  xor     eax, ecx
0x180017d67  and     eax, 8
0x180017d6a  xor     eax, ecx
0x180017d6c  mov     rcx, r11; hMem
0x180017d6f  mov     [rdi+60h], eax
0x180017d72  mov     edx, [r11+7Ch]
0x180017d76  shl     edx, 2
0x180017d79  xor     edx, eax
0x180017d7b  and     edx, 4
0x180017d7e  xor     edx, eax
0x180017d80  mov     [rdi+60h], edx
0x180017d83  mov     eax, [r11+80h]
0x180017d8a  mov     [rdi+68h], eax
0x180017d8d  mov     eax, [r11+84h]
0x180017d94  mov     [rdi+6Ch], eax
0x180017d97  mov     eax, [r11+88h]
0x180017d9e  shl     eax, 4
0x180017da1  xor     eax, edx
0x180017da3  and     eax, 10h
0x180017da6  xor     eax, edx
0x180017da8  mov     [rdi+60h], eax
0x180017dab  movups  xmm0, xmmword ptr [r11+8Ch]
0x180017db3  movups  xmmword ptr [rdi+70h], xmm0
0x180017db7  movups  xmm1, xmmword ptr [r11+9Ch]
0x180017dbf  movups  xmmword ptr [rdi+80h], xmm1
0x180017dc6  movups  xmm0, xmmword ptr [r11+0ACh]
0x180017dce  movups  xmmword ptr [rdi+90h], xmm0
0x180017dd5  movups  xmm1, xmmword ptr [r11+0BCh]
0x180017ddd  movups  xmmword ptr [rdi+0A0h], xmm1
0x180017de4  call    cs:__imp_LocalFree
0x180017deb  nop     dword ptr [rax+rax+00h]
0x180017df0  mov     rcx, [rbp+arg_0]
0x180017df4  lea     r8, [rbp+arg_18]
0x180017df8  mov     [rbp+arg_18], 0
0x180017e00  mov     edx, 0A0000004h
0x180017e05  mov     rax, [rcx]
0x180017e08  mov     rax, [rax+20h]
0x180017e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e11  test    eax, eax
0x180017e13  js      short loc_180017E2E
0x180017e15  mov     rcx, [rbp+arg_18]; hMem
0x180017e19  mov     eax, [rcx+8]
0x180017e1c  mov     [rdi+0D0h], eax
0x180017e22  call    cs:__imp_LocalFree
0x180017e29  nop     dword ptr [rax+rax+00h]
0x180017e2e  mov     rcx, [rbp+arg_0]
0x180017e32  mov     rax, [rcx]
0x180017e35  mov     rax, [rax+10h]
0x180017e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3e  mov     eax, ebx
0x180017e40  add     rsp, 20h
0x180017e44  pop     rdi
0x180017e45  pop     rbx
0x180017e46  pop     rbp
0x180017e47  retn
```
