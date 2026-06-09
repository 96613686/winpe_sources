# SockBuildMswsockProtocolInfoArray

- ea: `0x18000f068`
- end: `0x18000f254`
- name: `SockBuildMswsockProtocolInfoArray`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e428`

## callees

- `0x18000f068`
- `0x18000f3e0`
- `0x1800222f0`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f162`
- `ntdll!RtlFreeHeap` at `0x18000f162`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f0bc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f0bc`
- `WS2_32!WSCEnumProtocols` at `0x18000f0ee`
- `WS2_32!WSCEnumProtocols` at `0x18000f143`
- `WS2_32!WSCEnumProtocols` at `0x18000f0ee`
- `WS2_32!WSCEnumProtocols` at `0x18000f143`

## string_xrefs

- `0x18000f0a7`: `%SystemRoot%\system32\mswsock.dll`

## pseudocode

```c
__int64 __fastcall SockBuildMswsockProtocolInfoArray(struct _WSAPROTOCOL_INFOW **a1, int *a2)
{
  __int64 result; // rax
  struct _WSAPROTOCOL_INFOW *v4; // rax
  struct _WSAPROTOCOL_INFOW *v5; // rdi
  int v6; // esi
  int v7; // r14d
  struct _WSAPROTOCOL_INFOW *v8; // r15
  int IsMswsockCatalogEntry; // eax
  GUID ProviderId; // xmm0
  DWORD dwServiceFlags1; // edx
  DWORD dwProviderFlags; // r8d
  DWORD dwCatalogEntryId; // r9d
  DWORD iAddressFamily; // r10d
  unsigned int iSocketType; // r11d
  int iProtocol; // ebx
  __int64 v17; // rcx
  int *v18; // rcx
  int Errno; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwBufferLength; // [rsp+24h] [rbp-DCh] BYREF
  int *v21; // [rsp+28h] [rbp-D8h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF

  v21 = a2;
  dwBufferLength = 0;
  Errno = 0;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\mswsock.dll", Dst, 0x105u) - 1 > 0x104 )
    return 10107;
  Dst[261] = 0;
  dwBufferLength = 0;
  if ( WSCEnumProtocols(0, 0, &dwBufferLength, &Errno) != -1 )
    return 10107;
  result = (unsigned int)Errno;
  if ( Errno == 10055 )
  {
    v4 = (struct _WSAPROTOCOL_INFOW *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                                        SockPrivateHeap,
                                        0,
                                        dwBufferLength);
    v5 = v4;
    if ( v4 )
    {
      v6 = WSCEnumProtocols(0, v4, &dwBufferLength, &Errno);
      if ( v6 == -1 )
        goto LABEL_6;
      Errno = 0;
      v7 = 0;
      while ( v7 < v6 )
      {
        v8 = &v5[v7];
        IsMswsockCatalogEntry = SockIsMswsockCatalogEntry(v8, Dst);
        if ( IsMswsockCatalogEntry == -1 )
        {
          result = 10107;
          Errno = 10107;
          goto LABEL_14;
        }
        ProviderId = v8->ProviderId;
        dwServiceFlags1 = v8->dwServiceFlags1;
        dwProviderFlags = v8->dwProviderFlags;
        dwCatalogEntryId = v8->dwCatalogEntryId;
        iAddressFamily = v8->iAddressFamily;
        iSocketType = v8->iSocketType;
        iProtocol = v8->iProtocol;
        v17 = 44LL * v7++;
        *((_BYTE *)&v5->dwServiceFlags1 + v17) = IsMswsockCatalogEntry == 1;
        *(DWORD *)((char *)&v5->dwServiceFlags2 + v17) = dwServiceFlags1;
        *(DWORD *)((char *)&v5->dwServiceFlags3 + v17) = dwProviderFlags;
        *(DWORD *)((char *)&v5->dwServiceFlags4 + v17) = dwCatalogEntryId;
        *(DWORD *)((char *)&v5->dwProviderFlags + v17) = iAddressFamily;
        *(unsigned int *)((char *)&v5->ProviderId.Data1 + v17) = iSocketType;
        *(_DWORD *)((char *)&v5->ProviderId.Data2 + v17) = iProtocol;
        *(GUID *)&v5->ProviderId.Data4[v17] = ProviderId;
      }
      result = (unsigned int)Errno;
LABEL_14:
      if ( (_DWORD)result )
      {
LABEL_6:
        RtlFreeHeap(SockPrivateHeap, 0, v5);
        return (unsigned int)Errno;
      }
      else
      {
        v18 = v21;
        *a1 = v5;
        *v18 = v6;
      }
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f068  mov     [rsp-8+arg_10], rbx
0x18000f06d  push    rbp
0x18000f06e  push    rsi
0x18000f06f  push    rdi
0x18000f070  push    r12
0x18000f072  push    r13
0x18000f074  push    r14
0x18000f076  push    r15
0x18000f078  lea     rbp, [rsp-150h]
0x18000f080  sub     rsp, 250h
0x18000f087  mov     rax, cs:__security_cookie
0x18000f08e  xor     rax, rsp
0x18000f091  mov     [rbp+180h+var_40], rax
0x18000f098  mov     [rsp+280h+var_258], rdx
0x18000f09d  mov     r13, rcx
0x18000f0a0  xor     ebx, ebx
0x18000f0a2  lea     rdx, [rsp+280h+Dst]; lpDst
0x18000f0a7  lea     rcx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x18000f0ae  mov     [rsp+280h+dwBufferLength], ebx
0x18000f0b2  mov     r8d, 105h; nSize
0x18000f0b8  mov     [rsp+280h+Errno], ebx
0x18000f0bc  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f0c3  nop     dword ptr [rax+rax+00h]
0x18000f0c8  dec     eax
0x18000f0ca  cmp     eax, 104h
0x18000f0cf  ja      loc_18000F19D
0x18000f0d5  lea     r9, [rsp+280h+Errno]; lpErrno
0x18000f0da  mov     [rbp+180h+var_46], bx
0x18000f0e1  lea     r8, [rsp+280h+dwBufferLength]; lpdwBufferLength
0x18000f0e6  mov     [rsp+280h+dwBufferLength], ebx
0x18000f0ea  xor     edx, edx; lpProtocolBuffer
0x18000f0ec  xor     ecx, ecx; lpiProtocols
0x18000f0ee  call    cs:__imp_WSCEnumProtocols
0x18000f0f5  nop     dword ptr [rax+rax+00h]
0x18000f0fa  cmp     eax, 0FFFFFFFFh
0x18000f0fd  jnz     loc_18000F19D
0x18000f103  mov     eax, [rsp+280h+Errno]
0x18000f107  cmp     eax, 2747h
0x18000f10c  jnz     short loc_18000F172
0x18000f10e  mov     r8d, [rsp+280h+dwBufferLength]
0x18000f113  xor     edx, edx
0x18000f115  mov     rcx, cs:SockPrivateHeap
0x18000f11c  mov     rax, cs:SockAllocateHeapRoutine
0x18000f123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f128  mov     rdi, rax
0x18000f12b  test    rax, rax
0x18000f12e  jz      loc_18000F24A
0x18000f134  lea     r9, [rsp+280h+Errno]; lpErrno
0x18000f139  mov     rdx, rax; lpProtocolBuffer
0x18000f13c  lea     r8, [rsp+280h+dwBufferLength]; lpdwBufferLength
0x18000f141  xor     ecx, ecx; lpiProtocols
0x18000f143  call    cs:__imp_WSCEnumProtocols
0x18000f14a  nop     dword ptr [rax+rax+00h]
0x18000f14f  mov     esi, eax
0x18000f151  cmp     eax, 0FFFFFFFFh
0x18000f154  jnz     short loc_18000F1A4
0x18000f156  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000f15d  mov     r8, rdi; P
0x18000f160  xor     edx, edx; Flags
0x18000f162  call    cs:__imp_RtlFreeHeap
0x18000f169  nop     dword ptr [rax+rax+00h]
0x18000f16e  mov     eax, [rsp+280h+Errno]
0x18000f172  mov     rcx, [rbp+180h+var_40]
0x18000f179  xor     rcx, rsp; StackCookie
0x18000f17c  call    __security_check_cookie
0x18000f181  mov     rbx, [rsp+280h+arg_10]
0x18000f189  add     rsp, 250h
0x18000f190  pop     r15
0x18000f192  pop     r14
0x18000f194  pop     r13
0x18000f196  pop     r12
0x18000f198  pop     rdi
0x18000f199  pop     rsi
0x18000f19a  pop     rbp
0x18000f19b  retn
0x18000f19d  mov     eax, 277Bh
0x18000f1a2  jmp     short loc_18000F172
0x18000f1a4  mov     [rsp+280h+Errno], ebx
0x18000f1a8  mov     r14d, ebx
0x18000f1ab  cmp     r14d, esi
0x18000f1ae  jge     loc_18000F244
0x18000f1b4  movsxd  r12, r14d
0x18000f1b7  lea     rdx, [rsp+280h+Dst]
0x18000f1bc  imul    r15, r12, 274h
0x18000f1c3  add     r15, rdi
0x18000f1c6  mov     rcx, r15
0x18000f1c9  call    SockIsMswsockCatalogEntry
0x18000f1ce  cmp     eax, 0FFFFFFFFh
0x18000f1d1  jz      short loc_18000F223
0x18000f1d3  movups  xmm0, xmmword ptr [r15+14h]
0x18000f1d8  mov     edx, [r15]
0x18000f1db  mov     r8d, [r15+10h]
0x18000f1df  mov     r9d, [r15+24h]
0x18000f1e3  mov     r10d, [r15+4Ch]
0x18000f1e7  mov     r11d, [r15+58h]
0x18000f1eb  mov     ebx, [r15+5Ch]
0x18000f1ef  imul    rcx, r12, 2Ch ; ','
0x18000f1f3  cmp     eax, 1
0x18000f1f6  setz    al
0x18000f1f9  inc     r14d
0x18000f1fc  mov     [rcx+rdi], al
0x18000f1ff  mov     [rcx+rdi+4], edx
0x18000f203  mov     [rcx+rdi+8], r8d
0x18000f208  mov     [rcx+rdi+0Ch], r9d
0x18000f20d  mov     [rcx+rdi+10h], r10d
0x18000f212  mov     [rcx+rdi+14h], r11d
0x18000f217  mov     [rcx+rdi+18h], ebx
0x18000f21b  movdqu  xmmword ptr [rcx+rdi+1Ch], xmm0
0x18000f221  jmp     short loc_18000F1AB
0x18000f223  mov     eax, 277Bh
0x18000f228  mov     [rsp+280h+Errno], eax
0x18000f22c  test    eax, eax
0x18000f22e  jnz     loc_18000F156
0x18000f234  mov     rcx, [rsp+280h+var_258]
0x18000f239  mov     [r13+0], rdi
0x18000f23d  mov     [rcx], esi
0x18000f23f  jmp     loc_18000F172
0x18000f244  mov     eax, [rsp+280h+Errno]
0x18000f248  jmp     short loc_18000F22C
0x18000f24a  mov     eax, 8
0x18000f24f  jmp     loc_18000F172
```
