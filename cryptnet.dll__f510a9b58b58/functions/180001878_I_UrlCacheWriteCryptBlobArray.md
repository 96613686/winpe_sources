# I_UrlCacheWriteCryptBlobArray

- ea: `0x180001878`
- end: `0x180001954`
- name: `I_UrlCacheWriteCryptBlobArray`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001808`

## callees

- `0x180001878`
- `0x18000195c`
- `0x180001c80`
- `0x180005900`

## pseudocode

```c
__int64 __fastcall I_UrlCacheWriteCryptBlobArray(_WORD *a1, const void *a2, _DWORD *a3, __int64 a4, __int64 a5)
{
  _WORD *v6; // rdx
  unsigned int v9; // ebx
  HANDLE v11[3]; // [rsp+40h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  v11[0] = 0;
  v6 = 0;
  hObject = 0;
  if ( a4 && *(_DWORD *)a4 > 0x30u && *(_QWORD *)(a4 + 48) )
    v6 = *(_WORD **)(a4 + 48);
  if ( (unsigned int)I_UrlCacheCreateMetaDataAndContentFiles(a1, v6, (__int64)a2, 1, v11, (__int64 *)&hObject) )
    v9 = I_UrlCacheWriteCryptBlobArray2(a2, v11[0], hObject, a3, 0, a4, a5);
  else
    v9 = 0;
  if ( hObject )
    I_UrlCacheCloseHandle(hObject);
  if ( v11[0] )
    I_UrlCacheCloseHandle(v11[0]);
  return v9;
}

```

## disassembly

```asm
0x180001878  mov     rax, rsp
0x18000187b  mov     [rax+8], rbx
0x18000187f  mov     [rax+10h], rbp
0x180001883  push    r14
0x180001885  sub     rsp, 50h
0x180001889  mov     rbp, rdx
0x18000188c  mov     qword ptr [rax-18h], 0
0x180001894  xor     edx, edx; void *
0x180001896  mov     qword ptr [rax+20h], 0
0x18000189e  mov     rbx, r9
0x1800018a1  mov     r14, r8
0x1800018a4  test    r9, r9
0x1800018a7  jz      short loc_1800018B3
0x1800018a9  cmp     dword ptr [r9], 30h ; '0'
0x1800018ad  ja      loc_180001942
0x1800018b3  lea     rax, [rsp+58h+hObject]
0x1800018b8  mov     r9d, 1
0x1800018be  mov     [rsp+58h+var_30], rax; __int64
0x1800018c3  mov     r8, rbp
0x1800018c6  lea     rax, [rsp+58h+var_18]
0x1800018cb  mov     [rsp+58h+var_38], rax; __int64
0x1800018d0  call    I_UrlCacheCreateMetaDataAndContentFiles
0x1800018d5  test    eax, eax
0x1800018d7  jz      short loc_180001950
0x1800018d9  mov     rax, [rsp+58h+arg_20]
0x1800018e1  mov     r9, r14
0x1800018e4  mov     r8, [rsp+58h+hObject]
0x1800018e9  mov     rcx, rbp
0x1800018ec  mov     rdx, [rsp+58h+var_18]
0x1800018f1  mov     [rsp+58h+var_28], rax
0x1800018f6  mov     [rsp+58h+var_30], rbx
0x1800018fb  mov     [rsp+58h+var_38], 0
0x180001904  call    I_UrlCacheWriteCryptBlobArray2
0x180001909  mov     ebx, eax
0x18000190b  cmp     [rsp+58h+hObject], 0
0x180001911  jz      short loc_18000191D
0x180001913  mov     rcx, [rsp+58h+hObject]; hObject
0x180001918  call    I_UrlCacheCloseHandle
0x18000191d  cmp     [rsp+58h+var_18], 0
0x180001923  jz      short loc_18000192F
0x180001925  mov     rcx, [rsp+58h+var_18]; hObject
0x18000192a  call    I_UrlCacheCloseHandle
0x18000192f  mov     rbp, [rsp+58h+arg_8]
0x180001934  mov     eax, ebx
0x180001936  mov     rbx, [rsp+58h+arg_0]
0x18000193b  add     rsp, 50h
0x18000193f  pop     r14
0x180001941  retn
0x180001942  cmp     [r9+30h], rdx
0x180001946  cmovnz  rdx, [r9+30h]
0x18000194b  jmp     loc_1800018B3
0x180001950  xor     ebx, ebx
0x180001952  jmp     short loc_18000190B
```
