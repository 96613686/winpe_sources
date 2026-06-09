# BthServStartAutoConfigServiceMonitor(void)

- ea: `0x18001ca3c`
- end: `0x18001cdd7`
- name: `?BthServStartAutoConfigServiceMonitor@@YAXXZ`
- size: `923`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b6d8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x18000dfcc`
- `0x180010128`
- `0x180012004`
- `0x1800120b8`
- `0x18001ca3c`
- `0x18001d1a8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc12`

## pseudocode

```c
void BthServStartAutoConfigServiceMonitor(void)
{
  _BYTE *v0; // rcx
  char v1; // si
  bool v2; // dl
  __int64 v3; // r8
  int v4; // edx
  volatile signed __int32 *v5; // rbx
  bool v6; // dl
  bool v7; // dl
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rbx
  DWORD NumberOfBytesTransferred[2]; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE *v11; // [rsp+60h] [rbp-A8h] BYREF
  volatile signed __int32 *v12; // [rsp+68h] [rbp-A0h]
  _BYTE v13[304]; // [rsp+78h] [rbp-90h] BYREF

  NumberOfBytesTransferred[0] = 0;
  memset_0(v13, 0, 0x124u);
  v0 = WPP_GLOBAL_Control;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v0 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)&dword_1800470E4 )
    goto LABEL_54;
  BthServGlobals::GetSafeRadioHandle(&Globals, &v11);
  if ( !v11 || (char *)*v11 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v0 = WPP_GLOBAL_Control;
    v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
      goto LABEL_48;
    }
LABEL_49:
    v8 = v12;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        v9 = v12;
        (**(void (__fastcall ***)(volatile signed __int32 *, volatile signed __int32 *, __int64))v12)(v12, v8, v3);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
      goto LABEL_53;
    }
    goto LABEL_54;
  }
  if ( BthServOverlappedIoctl(*v11, 0x410000u, 0, 0, v13, 0x124u, NumberOfBytesTransferred)
    || NumberOfBytesTransferred[0] != 292 )
  {
    v0 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_48:
      v0 = WPP_GLOBAL_Control;
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      v5 = v12;
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v13[278] >= 2u )
  {
    pInterfaceGuid = LocalAlloc(0x40u, 0x80u);
    if ( pInterfaceGuid )
    {
      MonitorAutoConfigService();
      goto LABEL_53;
    }
    v0 = WPP_GLOBAL_Control;
    v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
      goto LABEL_53;
    }
  }
  else
  {
    v0 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_53:
      v0 = WPP_GLOBAL_Control;
    }
  }
LABEL_54:
  if ( v0 == (_BYTE *)&WPP_GLOBAL_Control || v0[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v0 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v0 + 5));
}

```

## disassembly

```asm
0x18001ca3c  mov     rax, rsp
0x18001ca3f  mov     [rax+8], rbx
0x18001ca43  mov     [rax+10h], rsi
0x18001ca47  mov     [rax+18h], r13
0x18001ca4b  push    rbp
0x18001ca4c  push    r14
0x18001ca4e  push    r15
0x18001ca50  lea     rbp, [rax-0C8h]
0x18001ca57  sub     rsp, 1B0h
0x18001ca5e  mov     rax, cs:__security_cookie
0x18001ca65  xor     rax, rsp
0x18001ca68  mov     [rbp+0C0h+var_20], rax
0x18001ca6f  and     [rsp+1C0h+NumberOfBytesTransferred], 0
0x18001ca74  lea     rcx, [rsp+1C0h+var_150]; void *
0x18001ca79  mov     ebx, 124h
0x18001ca7e  xor     edx, edx; Val
0x18001ca80  mov     r8d, ebx; Size
0x18001ca83  call    memset_0
0x18001ca88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca8f  lea     r14, WPP_GLOBAL_Control
0x18001ca96  mov     sil, 1
0x18001ca99  cmp     rcx, r14
0x18001ca9c  jz      short loc_18001CAA9
0x18001ca9e  cmp     byte ptr [rcx+19h], 4
0x18001caa2  jb      short loc_18001CAA9
0x18001caa4  mov     dl, sil
0x18001caa7  jmp     short loc_18001CAAB
0x18001caa9  xor     dl, dl
0x18001caab  lea     r15, WPP_RECORDER_INITIALIZED
0x18001cab2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001cab9  lea     r13, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001cac0  setnz   r8b
0x18001cac4  test    dl, dl
0x18001cac6  jnz     short loc_18001CACD
0x18001cac8  test    r8b, r8b
0x18001cacb  jz      short loc_18001CAED
0x18001cacd  mov     r9, [rcx+28h]
0x18001cad1  mov     rcx, [rcx+10h]
0x18001cad5  mov     [rsp+1C0h+var_188], r13
0x18001cada  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Ah
0x18001cae1  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caed  cmp     cs:dword_1800470E4, 0
0x18001caf4  jz      loc_18001CD6B
0x18001cafa  lea     rdx, [rsp+1C0h+var_168]
0x18001caff  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001cb06  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001cb0b  mov     rax, [rsp+1C0h+var_168]
0x18001cb10  test    rax, rax
0x18001cb13  jz      loc_18001CCCF
0x18001cb19  mov     rcx, [rax]; hFile
0x18001cb1c  lea     rax, [rcx-1]
0x18001cb20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001cb24  ja      loc_18001CCCF
0x18001cb2a  lea     rax, [rsp+1C0h+NumberOfBytesTransferred]
0x18001cb2f  xor     r9d, r9d; nInBufferSize
0x18001cb32  mov     [rsp+1C0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001cb37  xor     r8d, r8d; lpInBuffer
0x18001cb3a  lea     rax, [rsp+1C0h+var_150]
0x18001cb3f  mov     [rsp+1C0h+var_198], ebx; DWORD
0x18001cb43  mov     edx, 410000h; dwIoControlCode
0x18001cb48  mov     [rsp+1C0h+var_1A0], rax; void *
0x18001cb4d  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001cb52  test    eax, eax
0x18001cb54  jnz     loc_18001CC83
0x18001cb5a  cmp     [rsp+1C0h+NumberOfBytesTransferred], ebx
0x18001cb5e  jnz     loc_18001CC83
0x18001cb64  mov     rcx, [rsp+1C0h+var_160]
0x18001cb69  test    rcx, rcx
0x18001cb6c  jz      short loc_18001CBAC
0x18001cb6e  or      eax, 0FFFFFFFFh
0x18001cb71  lock xadd [rcx+8], eax
0x18001cb76  cmp     eax, 1
0x18001cb79  jnz     short loc_18001CBAC
0x18001cb7b  mov     rbx, [rsp+1C0h+var_160]
0x18001cb80  mov     rcx, rbx
0x18001cb83  mov     rax, [rbx]
0x18001cb86  mov     rax, [rax]
0x18001cb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb8e  or      eax, 0FFFFFFFFh
0x18001cb91  lock xadd [rbx+0Ch], eax
0x18001cb96  cmp     eax, 1
0x18001cb99  jnz     short loc_18001CBAC
0x18001cb9b  mov     rcx, [rsp+1C0h+var_160]
0x18001cba0  mov     rax, [rcx]
0x18001cba3  mov     rax, [rax+8]
0x18001cba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbac  movzx   eax, [rbp+0C0h+var_3A]
0x18001cbb3  cmp     al, 2
0x18001cbb5  jnb     short loc_18001CC0A
0x18001cbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbbe  cmp     rcx, r14
0x18001cbc1  jz      short loc_18001CBCE
0x18001cbc3  cmp     byte ptr [rcx+19h], 4
0x18001cbc7  jb      short loc_18001CBCE
0x18001cbc9  mov     dl, sil
0x18001cbcc  jmp     short loc_18001CBD0
0x18001cbce  xor     dl, dl
0x18001cbd0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001cbd7  setnz   r8b
0x18001cbdb  test    dl, dl
0x18001cbdd  jnz     short loc_18001CBE8
0x18001cbdf  test    r8b, r8b
0x18001cbe2  jz      loc_18001CD6B
0x18001cbe8  mov     r9, [rcx+28h]
0x18001cbec  mov     rcx, [rcx+10h]
0x18001cbf0  mov     [rsp+1C0h+var_178], eax
0x18001cbf4  mov     [rsp+1C0h+var_188], r13
0x18001cbf9  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Dh
0x18001cc00  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001cc05  jmp     loc_18001CD64
0x18001cc0a  mov     edx, 80h; uBytes
0x18001cc0f  lea     ecx, [rdx-40h]; uFlags
0x18001cc12  call    cs:__imp_LocalAlloc
0x18001cc19  nop     dword ptr [rax+rax+00h]
0x18001cc1e  mov     cs:pInterfaceGuid, rax
0x18001cc25  test    rax, rax
0x18001cc28  jnz     short loc_18001CC79
0x18001cc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc31  cmp     rcx, r14
0x18001cc34  jz      short loc_18001CC41
0x18001cc36  cmp     byte ptr [rcx+19h], 3
0x18001cc3a  jb      short loc_18001CC41
0x18001cc3c  mov     dl, sil
0x18001cc3f  jmp     short loc_18001CC43
0x18001cc41  xor     dl, dl
0x18001cc43  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001cc4a  setnz   r8b
0x18001cc4e  test    dl, dl
0x18001cc50  jnz     short loc_18001CC5B
0x18001cc52  test    r8b, r8b
0x18001cc55  jz      loc_18001CD6B
0x18001cc5b  mov     r9, [rcx+28h]
0x18001cc5f  mov     rcx, [rcx+10h]
0x18001cc63  mov     [rsp+1C0h+var_188], r13
0x18001cc68  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Eh
0x18001cc6f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cc74  jmp     loc_18001CD64
0x18001cc79  call    ?MonitorAutoConfigService@@YAXXZ; MonitorAutoConfigService(void)
0x18001cc7e  jmp     loc_18001CD64
0x18001cc83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc8a  cmp     rcx, r14
0x18001cc8d  jz      short loc_18001CC9A
0x18001cc8f  cmp     byte ptr [rcx+19h], 3
0x18001cc93  jb      short loc_18001CC9A
0x18001cc95  mov     dl, sil
0x18001cc98  jmp     short loc_18001CC9C
0x18001cc9a  xor     dl, dl
0x18001cc9c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001cca3  setnz   r8b
0x18001cca7  test    dl, dl
0x18001cca9  jnz     short loc_18001CCB0
0x18001ccab  test    r8b, r8b
0x18001ccae  jz      short loc_18001CD1C
0x18001ccb0  mov     r9, [rcx+28h]
0x18001ccb4  mov     rcx, [rcx+10h]
0x18001ccb8  mov     [rsp+1C0h+var_178], eax
0x18001ccbc  mov     [rsp+1C0h+var_188], r13
0x18001ccc1  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Bh
0x18001ccc8  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001cccd  jmp     short loc_18001CD15
0x18001cccf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccd6  cmp     rcx, r14
0x18001ccd9  jz      short loc_18001CCE6
0x18001ccdb  cmp     byte ptr [rcx+19h], 4
0x18001ccdf  jb      short loc_18001CCE6
0x18001cce1  mov     dl, sil
0x18001cce4  jmp     short loc_18001CCE8
0x18001cce6  xor     dl, dl
0x18001cce8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001ccef  setnz   r8b
0x18001ccf3  test    dl, dl
0x18001ccf5  jnz     short loc_18001CCFC
0x18001ccf7  test    r8b, r8b
0x18001ccfa  jz      short loc_18001CD1C
0x18001ccfc  mov     r9, [rcx+28h]
0x18001cd00  mov     rcx, [rcx+10h]
0x18001cd04  mov     [rsp+1C0h+var_188], r13
0x18001cd09  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Ch
0x18001cd10  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cd15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd1c  mov     rdx, [rsp+1C0h+var_160]
0x18001cd21  test    rdx, rdx
0x18001cd24  jz      short loc_18001CD6B
0x18001cd26  or      eax, 0FFFFFFFFh
0x18001cd29  lock xadd [rdx+8], eax
0x18001cd2e  cmp     eax, 1
0x18001cd31  jnz     short loc_18001CD64
0x18001cd33  mov     rbx, [rsp+1C0h+var_160]
0x18001cd38  mov     rcx, rbx
0x18001cd3b  mov     rax, [rbx]
0x18001cd3e  mov     rax, [rax]
0x18001cd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd46  or      eax, 0FFFFFFFFh
0x18001cd49  lock xadd [rbx+0Ch], eax
0x18001cd4e  cmp     eax, 1
0x18001cd51  jnz     short loc_18001CD64
0x18001cd53  mov     rcx, [rsp+1C0h+var_160]
0x18001cd58  mov     rax, [rcx]
0x18001cd5b  mov     rax, [rax+8]
0x18001cd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd6b  cmp     rcx, r14
0x18001cd6e  jz      short loc_18001CD76
0x18001cd70  cmp     byte ptr [rcx+19h], 4
0x18001cd74  jnb     short loc_18001CD79
0x18001cd76  xor     sil, sil
0x18001cd79  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001cd80  setnz   r8b
0x18001cd84  test    sil, sil
0x18001cd87  jnz     short loc_18001CD8E
0x18001cd89  test    r8b, r8b
0x18001cd8c  jz      short loc_18001CDAA
0x18001cd8e  mov     r9, [rcx+28h]
0x18001cd92  mov     dl, sil
0x18001cd95  mov     rcx, [rcx+10h]
0x18001cd99  mov     [rsp+1C0h+var_188], r13
0x18001cd9e  mov     word ptr [rsp+1C0h+lpNumberOfBytesTransferred], 0Fh
0x18001cda5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cdaa  mov     rcx, [rbp+0C0h+var_20]
0x18001cdb1  xor     rcx, rsp; StackCookie
0x18001cdb4  call    __security_check_cookie
0x18001cdb9  lea     r11, [rsp+1C0h+var_10]
0x18001cdc1  mov     rbx, [r11+20h]
0x18001cdc5  mov     rsi, [r11+28h]
0x18001cdc9  mov     r13, [r11+30h]
0x18001cdcd  mov     rsp, r11
0x18001cdd0  pop     r15
0x18001cdd2  pop     r14
0x18001cdd4  pop     rbp
0x18001cdd5  retn
```
