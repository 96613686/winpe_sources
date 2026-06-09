# NfsSrv4EnumeratePerVsOpenFile

- ea: `0x18001a53c`
- end: `0x18001a6ce`
- name: `NfsSrv4EnumeratePerVsOpenFile`
- size: `402`
- prototype: `__int64 __usercall@<rax>(HANDLE hDevice@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019edc`

## callees

- `0x1800181b8`
- `0x180018284`
- `0x18001a53c`
- `0x18001ae1c`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a69a`
- `KERNEL32!HeapFree` at `0x18001a69a`
- `KERNEL32!GetLastError` at `0x18001a611`
- `KERNEL32!GetLastError` at `0x18001a611`
- `KERNEL32!HeapAlloc` at `0x18001a5bf`
- `KERNEL32!HeapAlloc` at `0x18001a5bf`
- `KERNEL32!GetProcessHeap` at `0x18001a5a9`
- `KERNEL32!GetProcessHeap` at `0x18001a68c`
- `KERNEL32!GetProcessHeap` at `0x18001a5a9`
- `KERNEL32!GetProcessHeap` at `0x18001a68c`
- `KERNEL32!DeviceIoControl` at `0x18001a605`
- `KERNEL32!DeviceIoControl` at `0x18001a605`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4EnumeratePerVsOpenFile(HANDLE hDevice, __int128 *a2, __int64 a3, __int64 a4, __int64 *a5)
{
  HANDLE ProcessHeap; // rax
  unsigned int v9; // ebx
  unsigned int *lpOutBuffer; // rdi
  DWORD v11; // r15d
  __int128 *i; // r8
  DWORD LastError; // eax
  unsigned int *v14; // rsi
  unsigned int j; // ebp
  unsigned int v16; // eax
  __int64 v17; // r8
  HANDLE v18; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-88h] BYREF
  __int64 v21; // [rsp+48h] [rbp-80h]
  _BYTE v22[16]; // [rsp+50h] [rbp-78h] BYREF
  __int128 InBuffer; // [rsp+60h] [rbp-68h] BYREF
  __int64 v24; // [rsp+70h] [rbp-58h]

  v21 = a4;
  BytesReturned = 0;
  InBuffer = 0;
  v24 = 0;
  __0__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__std__QEAA_XZ(v22);
  InBuffer = *a2;
  v24 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = 8;
  lpOutBuffer = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x1000u);
  if ( lpOutBuffer )
  {
    v11 = 24;
    for ( i = &InBuffer; ; i = (__int128 *)(lpOutBuffer + 3) )
    {
      v9 = 0;
      if ( !DeviceIoControl(hDevice, 0x1000058Cu, i, v11, lpOutBuffer, 0x1000u, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError != 234 )
        {
          if ( LastError )
            break;
        }
      }
      v11 = lpOutBuffer[1];
      v14 = (unsigned int *)((char *)lpOutBuffer + lpOutBuffer[2]);
      for ( j = 0; j < *lpOutBuffer; ++j )
      {
        v16 = NfsSrv4PostOpenFileInstance((MI_Instance *)a5[3], (__int64)v14, a3, v21);
        v17 = *a5;
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64 *, _QWORD))(v17 + 160))(a5, v16);
          break;
        }
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(v17 + 32))(a5) )
        {
          v9 = 1223;
          goto LABEL_15;
        }
        v14 = (unsigned int *)((char *)v14 + *v14);
      }
      if ( v9 != 234 )
        break;
    }
LABEL_15:
    v18 = GetProcessHeap();
    HeapFree(v18, 0, lpOutBuffer);
  }
  __1___Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__0A__std___std__QEAA_XZ(v22);
  return v9;
}

```

## disassembly

```asm
0x18001a53c  push    rbx
0x18001a53e  push    rbp
0x18001a53f  push    rsi
0x18001a540  push    rdi
0x18001a541  push    r12
0x18001a543  push    r13
0x18001a545  push    r14
0x18001a547  push    r15
0x18001a549  sub     rsp, 88h
0x18001a550  mov     rax, cs:__security_cookie
0x18001a557  xor     rax, rsp
0x18001a55a  mov     [rsp+0C8h+var_50], rax
0x18001a55f  mov     [rsp+0C8h+var_80], r9
0x18001a564  mov     r13, r8
0x18001a567  mov     rbx, rdx
0x18001a56a  mov     r12, rcx
0x18001a56d  mov     r14, [rsp+0C8h+arg_20]
0x18001a575  mov     [rsp+0C8h+BytesReturned], 0
0x18001a57d  xorps   xmm0, xmm0
0x18001a580  xor     eax, eax
0x18001a582  movups  [rsp+0C8h+InBuffer], xmm0
0x18001a587  mov     [rsp+0C8h+var_58], rax
0x18001a58c  lea     rcx, [rsp+0C8h+var_78]
0x18001a591  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ
0x18001a596  nop
0x18001a597  movaps  xmm0, xmmword ptr [rbx]
0x18001a59a  movdqu  [rsp+0C8h+InBuffer], xmm0
0x18001a5a0  mov     [rsp+0C8h+var_58], 0
0x18001a5a9  call    cs:__imp_GetProcessHeap
0x18001a5af  mov     rcx, rax; hHeap
0x18001a5b2  mov     ebx, 8
0x18001a5b7  mov     r8d, 1000h; dwBytes
0x18001a5bd  mov     edx, ebx; dwFlags
0x18001a5bf  call    cs:__imp_HeapAlloc
0x18001a5c5  mov     rdi, rax
0x18001a5c8  test    rax, rax
0x18001a5cb  jz      loc_18001A6A1
0x18001a5d1  lea     r15d, [rbx+10h]
0x18001a5d5  lea     r8, [rsp+0C8h+InBuffer]; lpInBuffer
0x18001a5da  mov     [rsp+0C8h+lpOverlapped], 0; lpOverlapped
0x18001a5e3  lea     rax, [rsp+0C8h+BytesReturned]
0x18001a5e8  mov     [rsp+0C8h+lpBytesReturned], rax; lpBytesReturned
0x18001a5ed  mov     [rsp+0C8h+nOutBufferSize], 1000h; nOutBufferSize
0x18001a5f5  mov     [rsp+0C8h+lpOutBuffer], rdi; lpOutBuffer
0x18001a5fa  mov     r9d, r15d; nInBufferSize
0x18001a5fd  mov     edx, 1000058Ch; dwIoControlCode
0x18001a602  mov     rcx, r12; hDevice
0x18001a605  call    cs:__imp_DeviceIoControl
0x18001a60b  xor     ebx, ebx
0x18001a60d  test    eax, eax
0x18001a60f  jnz     short loc_18001A624
0x18001a611  call    cs:__imp_GetLastError
0x18001a617  mov     ebx, eax
0x18001a619  cmp     eax, 0EAh
0x18001a61e  jz      short loc_18001A624
0x18001a620  test    eax, eax
0x18001a622  jnz     short loc_18001A68C
0x18001a624  mov     r15d, [rdi+4]
0x18001a628  mov     esi, [rdi+8]
0x18001a62b  add     rsi, rdi
0x18001a62e  xor     ebp, ebp
0x18001a630  cmp     ebp, [rdi]
0x18001a632  jnb     short loc_18001A676
0x18001a634  mov     r9, [rsp+0C8h+var_80]
0x18001a639  mov     r8, r13
0x18001a63c  mov     rdx, rsi
0x18001a63f  mov     rcx, [r14+18h]; self
0x18001a643  call    NfsSrv4PostOpenFileInstance
0x18001a648  mov     r8, [r14]
0x18001a64b  mov     rcx, r14
0x18001a64e  test    eax, eax
0x18001a650  jnz     short loc_18001A668
0x18001a652  mov     rax, [r8+20h]
0x18001a656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a65b  test    al, al
0x18001a65d  jnz     short loc_18001A687
0x18001a65f  mov     eax, [rsi]
0x18001a661  add     rsi, rax
0x18001a664  inc     ebp
0x18001a666  jmp     short loc_18001A630
0x18001a668  mov     edx, eax
0x18001a66a  mov     rax, [r8+0A0h]
0x18001a671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a676  cmp     ebx, 0EAh
0x18001a67c  jnz     short loc_18001A68C
0x18001a67e  lea     r8, [rdi+0Ch]
0x18001a682  jmp     loc_18001A5DA
0x18001a687  mov     ebx, 4C7h
0x18001a68c  call    cs:__imp_GetProcessHeap
0x18001a692  mov     rcx, rax; hHeap
0x18001a695  mov     r8, rdi; lpMem
0x18001a698  xor     edx, edx; dwFlags
0x18001a69a  call    cs:__imp_HeapFree
0x18001a6a0  nop
0x18001a6a1  lea     rcx, [rsp+0C8h+var_78]
0x18001a6a6  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x18001a6ab  mov     eax, ebx
0x18001a6ad  mov     rcx, [rsp+0C8h+var_50]
0x18001a6b2  xor     rcx, rsp; StackCookie
0x18001a6b5  call    __security_check_cookie
0x18001a6ba  add     rsp, 88h
0x18001a6c1  pop     r15
0x18001a6c3  pop     r14
0x18001a6c5  pop     r13
0x18001a6c7  pop     r12
0x18001a6c9  pop     rdi
0x18001a6ca  pop     rsi
0x18001a6cb  pop     rbp
0x18001a6cc  pop     rbx
0x18001a6cd  retn
```
