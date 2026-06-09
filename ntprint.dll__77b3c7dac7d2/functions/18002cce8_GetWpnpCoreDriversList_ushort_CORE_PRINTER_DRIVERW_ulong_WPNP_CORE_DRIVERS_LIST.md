# GetWpnpCoreDriversList(ushort *,_CORE_PRINTER_DRIVERW *,ulong,_WPNP_CORE_DRIVERS_LIST * *)

- ea: `0x18002cce8`
- end: `0x18002ce3e`
- name: `?GetWpnpCoreDriversList@@YAJPEAGPEAU_CORE_PRINTER_DRIVERW@@KPEAPEAU_WPNP_CORE_DRIVERS_LIST@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _CORE_PRINTER_DRIVERW *, unsigned int, struct _WPNP_CORE_DRIVERS_LIST **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d300`

## callees

- `0x180002f48`
- `0x18000b200`
- `0x18002c51c`
- `0x18002cce8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ce1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ce1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cd4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cd4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce0f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002cd96`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002cd96`

## pseudocode

```c
__int64 __fastcall GetWpnpCoreDriversList(
        unsigned __int16 *a1,
        struct _CORE_PRINTER_DRIVERW *a2,
        unsigned int a3,
        struct _WPNP_CORE_DRIVERS_LIST **a4)
{
  __int64 v4; // rbp
  unsigned __int16 *v7; // rdi
  NCoreLibrary *v8; // rcx
  HLOCAL v9; // rsi
  int LastErrorAsFailHR; // ebx
  unsigned int v11; // r14d
  HRESULT v12; // eax
  __int64 v13; // r14
  unsigned int v14; // edi
  void *v15; // rcx
  struct _WPNP_CORE_DRIVERS_LIST *v17; // [rsp+80h] [rbp+8h] BYREF

  v4 = a3;
  v17 = 0;
  v7 = a1;
  if ( !a1 || !*a1 || !a2 || !a3 || !a4 )
    return (unsigned int)-2147024809;
  *a4 = 0;
  v9 = LocalAlloc(0x40u, 8 * a3);
  if ( v9 )
  {
    LastErrorAsFailHR = 0;
  }
  else
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
  }
  memset_0(v9, 0, 8 * v4);
  v11 = 0;
  do
  {
    if ( v11 >= (unsigned int)v4 )
      break;
    v12 = StringFromIID(&a2[v11].CoreDriverGUID, (LPOLESTR *)v9 + v11);
    ++v11;
    LastErrorAsFailHR = v12;
  }
  while ( v12 >= 0 );
  if ( LastErrorAsFailHR >= 0 )
  {
    while ( v7 )
    {
      if ( *v7 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v7[v13] );
        LastErrorAsFailHR = AddCoreDriverToList(a2, v4, (unsigned __int16 **)v9, v7, &v17);
        v7 += v13 + 1;
        if ( LastErrorAsFailHR >= 0 )
          continue;
      }
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_20;
      break;
    }
    *a4 = v17;
  }
LABEL_20:
  if ( v9 )
  {
    v14 = 0;
    do
    {
      v15 = (void *)*((_QWORD *)v9 + v14);
      if ( v15 )
        CoTaskMemFree(v15);
      ++v14;
    }
    while ( v14 < (unsigned int)v4 );
    LocalFree(v9);
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002cce8  mov     rax, rsp
0x18002cceb  push    rbx
0x18002ccec  push    rbp
0x18002cced  push    rsi
0x18002ccee  push    rdi
0x18002ccef  push    r12
0x18002ccf1  push    r13
0x18002ccf3  push    r14
0x18002ccf5  push    r15
0x18002ccf7  sub     rsp, 38h
0x18002ccfb  xor     r13d, r13d
0x18002ccfe  mov     ebp, r8d
0x18002cd01  mov     [rax+8], r13
0x18002cd05  mov     r15, r9
0x18002cd08  mov     r12, rdx
0x18002cd0b  mov     rdi, rcx
0x18002cd0e  test    rcx, rcx
0x18002cd11  jz      loc_18002CE26
0x18002cd17  cmp     [rcx], r13w
0x18002cd1b  jz      loc_18002CE26
0x18002cd21  test    rdx, rdx
0x18002cd24  jz      loc_18002CE26
0x18002cd2a  test    r8d, r8d
0x18002cd2d  jz      loc_18002CE26
0x18002cd33  test    r9, r9
0x18002cd36  jz      loc_18002CE26
0x18002cd3c  lea     edx, ds:0[rbp*8]; uBytes
0x18002cd43  mov     [r9], r13
0x18002cd46  lea     ecx, [r13+40h]; uFlags
0x18002cd4a  call    cs:__imp_LocalAlloc
0x18002cd50  mov     rsi, rax
0x18002cd53  test    rax, rax
0x18002cd56  jz      short loc_18002CD5D
0x18002cd58  mov     ebx, r13d
0x18002cd5b  jmp     short loc_18002CD6C
0x18002cd5d  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002cd62  mov     ebx, eax
0x18002cd64  test    eax, eax
0x18002cd66  js      loc_18002CE2B
0x18002cd6c  mov     r8, rbp
0x18002cd6f  xor     edx, edx; Val
0x18002cd71  shl     r8, 3; Size
0x18002cd75  mov     rcx, rsi; void *
0x18002cd78  call    memset_0
0x18002cd7d  mov     r14d, r13d
0x18002cd80  cmp     r14d, ebp
0x18002cd83  jnb     short loc_18002CDA5
0x18002cd85  mov     eax, r14d
0x18002cd88  imul    rcx, rax, 228h
0x18002cd8f  lea     rdx, [rsi+rax*8]; lplpsz
0x18002cd93  add     rcx, r12; rclsid
0x18002cd96  call    cs:__imp_StringFromIID
0x18002cd9c  inc     r14d
0x18002cd9f  mov     ebx, eax
0x18002cda1  test    eax, eax
0x18002cda3  jns     short loc_18002CD80
0x18002cda5  test    ebx, ebx
0x18002cda7  js      short loc_18002CDFC
0x18002cda9  test    rdi, rdi
0x18002cdac  jz      short loc_18002CDF1
0x18002cdae  cmp     [rdi], r13w
0x18002cdb2  jz      short loc_18002CDED
0x18002cdb4  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002cdb8  inc     r14
0x18002cdbb  cmp     [rdi+r14*2], r13w
0x18002cdc0  jnz     short loc_18002CDB8
0x18002cdc2  lea     rax, [rsp+78h+arg_0]
0x18002cdca  mov     r9, rdi; unsigned __int16 *
0x18002cdcd  mov     r8, rsi; unsigned __int16 **
0x18002cdd0  mov     [rsp+78h+var_58], rax; struct _WPNP_CORE_DRIVERS_LIST **
0x18002cdd5  mov     edx, ebp; unsigned int
0x18002cdd7  mov     rcx, r12; struct _CORE_PRINTER_DRIVERW *
0x18002cdda  call    ?AddCoreDriverToList@@YAJPEAU_CORE_PRINTER_DRIVERW@@KPEAPEAGPEAGPEAPEAU_WPNP_CORE_DRIVERS_LIST@@@Z; AddCoreDriverToList(_CORE_PRINTER_DRIVERW *,ulong,ushort * *,ushort *,_WPNP_CORE_DRIVERS_LIST * *)
0x18002cddf  lea     rdi, [rdi+r14*2]
0x18002cde3  mov     ebx, eax
0x18002cde5  add     rdi, 2
0x18002cde9  test    eax, eax
0x18002cdeb  jns     short loc_18002CDA9
0x18002cded  test    ebx, ebx
0x18002cdef  js      short loc_18002CDFC
0x18002cdf1  mov     rax, [rsp+78h+arg_0]
0x18002cdf9  mov     [r15], rax
0x18002cdfc  test    rsi, rsi
0x18002cdff  jz      short loc_18002CE2B
0x18002ce01  mov     edi, r13d
0x18002ce04  mov     eax, edi
0x18002ce06  mov     rcx, [rsi+rax*8]; pv
0x18002ce0a  test    rcx, rcx
0x18002ce0d  jz      short loc_18002CE15
0x18002ce0f  call    cs:__imp_CoTaskMemFree
0x18002ce15  inc     edi
0x18002ce17  cmp     edi, ebp
0x18002ce19  jb      short loc_18002CE04
0x18002ce1b  mov     rcx, rsi; hMem
0x18002ce1e  call    cs:__imp_LocalFree
0x18002ce24  jmp     short loc_18002CE2B
0x18002ce26  mov     ebx, 80070057h
0x18002ce2b  mov     eax, ebx
0x18002ce2d  add     rsp, 38h
0x18002ce31  pop     r15
0x18002ce33  pop     r14
0x18002ce35  pop     r13
0x18002ce37  pop     r12
0x18002ce39  pop     rdi
0x18002ce3a  pop     rsi
0x18002ce3b  pop     rbp
0x18002ce3c  pop     rbx
0x18002ce3d  retn
```
