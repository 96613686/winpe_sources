# MemFree(x)

- ea: `0x1000b200`
- end: `0x1000b2b3`
- name: `_MemFree@4`
- size: `179`
- prototype: ``
- caller_count: `71`
- callee_count: `3`
- tags: ``

## callers

- `0x1000a010`
- `0x1000a1f0`
- `0x1000a260`
- `0x1000a350`
- `0x1000a470`
- `0x1000a8c0`
- `0x1000b310`
- `0x1000c150`
- `0x1000c370`
- `0x1000cbf0`
- `0x1000d1c0`
- `0x1000d2c0`
- `0x1000d7a0`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000e3b0`
- `0x1000e950`
- `0x10010450`
- `0x10011310`
- `0x10011870`
- `0x10011d90`
- `0x10013ff0`
- `0x10014070`
- `0x100140b0`
- `0x10014100`
- `0x100141b0`
- `0x10014200`
- `0x10014270`
- `0x10014320`
- `0x10014400`
- `0x100161d0`
- `0x10016620`
- `0x100168a0`
- `0x10016990`
- `0x10016a10`
- `0x10018b90`
- `0x10019f20`
- `0x1001c420`
- `0x1001ca20`
- `0x1001d270`
- `0x1001d440`
- `0x1001d4b0`
- `0x1001d570`
- `0x1001e1e0`
- `0x1001eaf0`
- `0x1001f060`
- `0x1001f090`
- `0x1001f110`
- `0x1001f320`
- `0x10020080`

## callees

- `0x1000af50`
- `0x1000afd0`
- `0x1000b200`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1000b221`
- `KERNEL32!GlobalUnlock` at `0x1000b221`
- `KERNEL32!GlobalFree` at `0x1000b228`
- `KERNEL32!GlobalFree` at `0x1000b228`

## pseudocode

```c
_DWORD *__stdcall MemFree(_DWORD *a1)
{
  _DWORD *result; // eax
  int v2; // ebx
  _DWORD *v3; // esi
  void *v4; // esi
  int v5; // edi
  int v6; // ecx

  result = a1;
  if ( a1 )
  {
    v2 = *(a1 - 2);
    v3 = a1 - 3;
    if ( v2 )
    {
      if ( *v3 == 1 )
      {
        v4 = (void *)*(a1 - 1);
        if ( v4 )
        {
          GlobalUnlock((HGLOBAL)*(a1 - 1));
          return GlobalFree(v4);
        }
      }
      else
      {
        v5 = 0;
        v6 = dword_10040F6C;
        if ( dword_10040F6C )
        {
          while ( 1 )
          {
            result = (_DWORD *)(v6 + *(_DWORD *)(v6 + 4));
            if ( v3 == result )
            {
              *(_DWORD *)(v6 + 4) += v2;
              v3 = (_DWORD *)v6;
              goto LABEL_16;
            }
            if ( (_DWORD *)((char *)v3 + v2) == (_DWORD *)v6 )
              break;
            v5 = v6;
            v6 = *(_DWORD *)(v6 + 8);
            if ( !v6 )
              goto LABEL_10;
          }
          if ( v5 )
          {
            *(_DWORD *)(v5 + 8) = v3;
            v3[2] = *(_DWORD *)(v6 + 8);
            v3[1] += *(_DWORD *)(v6 + 4);
          }
          else
          {
            v3[2] = *(_DWORD *)(v6 + 8);
            v3[1] += *(_DWORD *)(v6 + 4);
            dword_10040F6C = (int)(a1 - 3);
          }
LABEL_16:
          result = (_DWORD *)AttemptToFreePage(v3);
          if ( result != (_DWORD *)1 )
            return (_DWORD *)AttemptToMerge(v3, v5);
        }
        else
        {
LABEL_10:
          v3[2] = dword_10040F6C;
          dword_10040F6C = (int)(a1 - 3);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000b200  mov     eax, [esp+arg_0]
0x1000b204  test    eax, eax
0x1000b206  jz      short locret_1000B269
0x1000b208  push    ebx
0x1000b209  mov     ebx, [eax-8]
0x1000b20c  push    esi
0x1000b20d  lea     esi, [eax-0Ch]
0x1000b210  test    ebx, ebx
0x1000b212  jz      short loc_1000B267
0x1000b214  cmp     dword ptr [esi], 1
0x1000b217  jnz     short loc_1000B233
0x1000b219  mov     esi, [eax-4]
0x1000b21c  test    esi, esi
0x1000b21e  jz      short loc_1000B267
0x1000b220  push    esi; hMem
0x1000b221  call    ds:__imp__GlobalUnlock@4; GlobalUnlock(x)
0x1000b227  push    esi; hMem
0x1000b228  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x1000b22e  pop     esi
0x1000b22f  pop     ebx
0x1000b230  retn    4
0x1000b233  push    ebp
0x1000b234  mov     ebp, dword_10040F6C
0x1000b23a  lea     edx, [ebx+esi]
0x1000b23d  push    edi
0x1000b23e  xor     edi, edi
0x1000b240  mov     ecx, ebp
0x1000b242  test    ebp, ebp
0x1000b244  jz      short loc_1000B25C
0x1000b246  mov     eax, [ecx+4]
0x1000b249  add     eax, ecx
0x1000b24b  cmp     esi, eax
0x1000b24d  jz      short loc_1000B295
0x1000b24f  cmp     edx, ecx
0x1000b251  jz      short loc_1000B26C
0x1000b253  mov     edi, ecx
0x1000b255  mov     ecx, [ecx+8]
0x1000b258  test    ecx, ecx
0x1000b25a  jnz     short loc_1000B246
0x1000b25c  mov     [esi+8], ebp
0x1000b25f  mov     dword_10040F6C, esi
0x1000b265  pop     edi
0x1000b266  pop     ebp
0x1000b267  pop     esi
0x1000b268  pop     ebx
0x1000b269  retn    4
0x1000b26c  test    edi, edi
0x1000b26e  jnz     short loc_1000B284
0x1000b270  mov     eax, [ecx+8]
0x1000b273  mov     [esi+8], eax
0x1000b276  mov     eax, [ecx+4]
0x1000b279  add     [esi+4], eax
0x1000b27c  mov     dword_10040F6C, esi
0x1000b282  jmp     short loc_1000B29A
0x1000b284  mov     [edi+8], esi
0x1000b287  mov     eax, [ecx+8]
0x1000b28a  mov     [esi+8], eax
0x1000b28d  mov     eax, [ecx+4]
0x1000b290  add     [esi+4], eax
0x1000b293  jmp     short loc_1000B29A
0x1000b295  add     [ecx+4], ebx
0x1000b298  mov     esi, ecx
0x1000b29a  push    esi
0x1000b29b  call    AttemptToFreePage
0x1000b2a0  cmp     eax, 1
0x1000b2a3  jz      short loc_1000B265
0x1000b2a5  push    edi
0x1000b2a6  push    esi
0x1000b2a7  call    AttemptToMerge
0x1000b2ac  pop     edi
0x1000b2ad  pop     ebp
0x1000b2ae  pop     esi
0x1000b2af  pop     ebx
0x1000b2b0  retn    4
```
