# Mcast_FreeIoContext

- ea: `0x18001d100`
- end: `0x18001d228`
- name: `Mcast_FreeIoContext`
- size: `296`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180001880`
- `0x18001d084`
- `0x18001d100`
- `0x18001d230`
- `0x18004c970`

## callees

- `0x18000b130`
- `0x18001d100`
- `0x18001d968`
- `0x18001da64`
- `0x18003ae2c`
- `0x180040928`
- `0x180086f24`

## import_xrefs

- `DNSAPI!Socket_CloseEx` at `0x18001d1cd`
- `DNSAPI!Socket_CloseEx` at `0x18001d1cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d1f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d209`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d209`

## pseudocode

```c
void __fastcall Mcast_FreeIoContext(char *a1, int a2)
{
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rdi
  void *v8; // rcx

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 16, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, a1);
  Mcast_PrintIoContext(a1);
  if ( a1 )
  {
    v4 = *((_QWORD *)a1 + 2);
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      Socket_CloseEx(v4, 0);
      *((_QWORD *)a1 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 6);
    if ( v5 )
    {
      ThreadShutdownWait(v5);
      v8 = (void *)*((_QWORD *)a1 + 6);
      if ( v8 )
      {
        CloseHandle(v8);
        *((_QWORD *)a1 + 6) = 0;
      }
    }
    v6 = (void *)*((_QWORD *)a1 + 5);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)a1 + 5) = 0;
    }
    Packet_FreeMsgBuf(*((void **)a1 + 13));
    while ( 1 )
    {
      v7 = *(_QWORD *)a1;
      if ( !*(_QWORD *)a1 )
        break;
      Mcast_RemoveContextList(*(_QWORD *)a1);
      Mcast_FreeIoContext(v7, 1);
    }
    if ( *((_DWORD *)a1 + 24) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
      *((_DWORD *)a1 + 24) = 0;
    }
    if ( a2 )
      MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x18001d100  mov     [rsp+arg_0], rbx
0x18001d105  mov     [rsp+arg_8], rsi
0x18001d10a  push    rdi
0x18001d10b  sub     rsp, 20h
0x18001d10f  mov     esi, edx
0x18001d111  mov     rbx, rcx
0x18001d114  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001d11b  jnz     loc_18001D1AD
0x18001d121  mov     rcx, rbx
0x18001d124  call    Mcast_PrintIoContext
0x18001d129  test    rbx, rbx
0x18001d12c  jz      short loc_18001D186
0x18001d12e  mov     rcx, [rbx+10h]
0x18001d132  lea     rax, [rcx-1]
0x18001d136  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d13a  jbe     loc_18001D1CB
0x18001d140  mov     rcx, [rbx+30h]; hThread
0x18001d144  test    rcx, rcx
0x18001d147  jnz     loc_18001D1E0
0x18001d14d  mov     rcx, [rbx+28h]; hObject
0x18001d151  test    rcx, rcx
0x18001d154  jz      short loc_18001D164
0x18001d156  call    cs:__imp_CloseHandle
0x18001d15c  mov     qword ptr [rbx+28h], 0
0x18001d164  mov     rcx, [rbx+68h]; void *
0x18001d168  call    Packet_FreeMsgBuf
0x18001d16d  mov     rdi, [rbx]
0x18001d170  test    rdi, rdi
0x18001d173  jnz     short loc_18001D196
0x18001d175  cmp     [rbx+60h], edi
0x18001d178  jnz     loc_18001D205
0x18001d17e  test    esi, esi
0x18001d180  jnz     loc_18001D21B
0x18001d186  mov     rbx, [rsp+28h+arg_0]
0x18001d18b  mov     rsi, [rsp+28h+arg_8]
0x18001d190  add     rsp, 20h
0x18001d194  pop     rdi
0x18001d195  retn
0x18001d196  mov     rcx, rdi
0x18001d199  call    Mcast_RemoveContextList
0x18001d19e  mov     edx, 1
0x18001d1a3  mov     rcx, rdi
0x18001d1a6  call    Mcast_FreeIoContext
0x18001d1ab  jmp     short loc_18001D16D
0x18001d1ad  mov     edx, 10h
0x18001d1b2  lea     r8, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids
0x18001d1b9  mov     ecx, 40Bh
0x18001d1be  mov     r9, rbx
0x18001d1c1  call    WPP_SF_q
0x18001d1c6  jmp     loc_18001D121
0x18001d1cb  xor     edx, edx
0x18001d1cd  call    cs:__imp_Socket_CloseEx
0x18001d1d3  mov     qword ptr [rbx+10h], 0
0x18001d1db  jmp     loc_18001D140
0x18001d1e0  call    ThreadShutdownWait
0x18001d1e5  mov     rcx, [rbx+30h]; hObject
0x18001d1e9  test    rcx, rcx
0x18001d1ec  jz      loc_18001D14D
0x18001d1f2  call    cs:__imp_CloseHandle
0x18001d1f8  mov     qword ptr [rbx+30h], 0
0x18001d200  jmp     loc_18001D14D
0x18001d205  lea     rcx, [rbx+38h]; lpCriticalSection
0x18001d209  call    cs:__imp_DeleteCriticalSection
0x18001d20f  mov     dword ptr [rbx+60h], 0
0x18001d216  jmp     loc_18001D17E
0x18001d21b  mov     rcx, rbx; void *
0x18001d21e  call    MIDL_user_free
0x18001d223  jmp     loc_18001D186
```
