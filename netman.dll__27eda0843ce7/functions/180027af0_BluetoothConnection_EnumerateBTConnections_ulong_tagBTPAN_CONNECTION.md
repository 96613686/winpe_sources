# BluetoothConnection::EnumerateBTConnections(ulong *,tagBTPAN_CONNECTION * *)

- ea: `0x180027af0`
- end: `0x180027c2e`
- name: `?EnumerateBTConnections@BluetoothConnection@@UEAAJPEAKPEAPEAUtagBTPAN_CONNECTION@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, unsigned int *, struct tagBTPAN_CONNECTION **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180027af0`
- `0x180032c3c`
- `0x180032ff8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c12`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::EnumerateBTConnections(
        BluetoothConnection *this,
        unsigned int *a2,
        struct tagBTPAN_CONNECTION **a3)
{
  signed int v5; // ebx
  unsigned int v6; // edi
  unsigned int v7; // esi
  LPVOID v8; // rax
  __int64 v9; // rcx
  void *v10; // r14
  struct tagBTPAN_CONNECTION *v11; // rax
  __int64 v12; // r8
  _WORD *v13; // rcx
  int v15; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 18) )
  {
    if ( a2 && a3 )
    {
      v6 = 1;
      *a2 = 0;
      v15 = 1;
      v7 = 0;
      *a3 = 0;
      do
      {
        v8 = CoTaskMemAlloc(8LL * v6);
        v10 = v8;
        if ( !v8 )
        {
          LOWORD(v5) = 14;
          goto LABEL_16;
        }
        v5 = BTEnumerateConnections(v8, &v15);
        if ( v5 )
        {
          CoTaskMemFree(v10);
          v6 = v15;
          if ( v5 != 122 )
            break;
          v6 = v15 + 3;
          v15 += 3;
          ++v7;
        }
        else
        {
          v6 = v15;
        }
      }
      while ( v5 == 122 && v7 < 0xA );
      if ( v5 <= 0 )
        goto LABEL_17;
LABEL_16:
      v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_17:
      if ( !v5 )
      {
        if ( v6 )
        {
          if ( v6 != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v9);
          v11 = (struct tagBTPAN_CONNECTION *)CoTaskMemAlloc(8LL * v6);
          *a3 = v11;
          if ( v11 )
          {
            v12 = 0;
            *a2 = v6;
            do
            {
              *((_WORD *)*a3 + 4 * v12 + 3) = *((_WORD *)v10 + 4 * v12 + 3);
              v13 = *a3;
              *(_DWORD *)&v13[4 * v12] = *((_DWORD *)v10 + 2 * v12);
              v13[4 * v12 + 2] = *((_WORD *)v10 + 4 * v12 + 2);
              v12 = (unsigned int)(v12 + 1);
            }
            while ( (unsigned int)v12 < v6 );
          }
          else
          {
            v5 = -2147024882;
          }
        }
        else
        {
          v5 = 1;
        }
        CoTaskMemFree(v10);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180027af0  push    rbx
0x180027af2  push    rbp
0x180027af3  push    rsi
0x180027af4  push    rdi
0x180027af5  push    r14
0x180027af7  push    r15
0x180027af9  sub     rsp, 28h
0x180027afd  cmp     dword ptr [rcx+48h], 0
0x180027b01  mov     r15, r8
0x180027b04  mov     rbp, rdx
0x180027b07  jnz     short loc_180027B13
0x180027b09  mov     ebx, 8000FFFFh
0x180027b0e  jmp     loc_180027C1F
0x180027b13  test    rbp, rbp
0x180027b16  jz      loc_180027C1A
0x180027b1c  test    r15, r15
0x180027b1f  jz      loc_180027C1A
0x180027b25  mov     edi, 1
0x180027b2a  mov     dword ptr [rdx], 0
0x180027b30  mov     [rsp+58h+arg_0], edi
0x180027b34  xor     esi, esi
0x180027b36  mov     qword ptr [r8], 0
0x180027b3d  mov     ecx, edi
0x180027b3f  shl     rcx, 3; cb
0x180027b43  call    cs:__imp_CoTaskMemAlloc
0x180027b49  mov     r14, rax
0x180027b4c  test    rax, rax
0x180027b4f  jz      short loc_180027B95
0x180027b51  lea     rdx, [rsp+58h+arg_0]
0x180027b56  mov     rcx, rax
0x180027b59  call    BTEnumerateConnections
0x180027b5e  mov     ebx, eax
0x180027b60  test    eax, eax
0x180027b62  jz      short loc_180027B81
0x180027b64  mov     rcx, r14; pv
0x180027b67  call    cs:__imp_CoTaskMemFree
0x180027b6d  mov     edi, [rsp+58h+arg_0]
0x180027b71  cmp     ebx, 7Ah ; 'z'
0x180027b74  jnz     short loc_180027B8F
0x180027b76  add     edi, 3
0x180027b79  mov     [rsp+58h+arg_0], edi
0x180027b7d  inc     esi
0x180027b7f  jmp     short loc_180027B85
0x180027b81  mov     edi, [rsp+58h+arg_0]
0x180027b85  cmp     ebx, 7Ah ; 'z'
0x180027b88  jnz     short loc_180027B8F
0x180027b8a  cmp     esi, 0Ah
0x180027b8d  jb      short loc_180027B3D
0x180027b8f  test    ebx, ebx
0x180027b91  jg      short loc_180027B9A
0x180027b93  jmp     short loc_180027BA3
0x180027b95  mov     ebx, 0Eh
0x180027b9a  movzx   ebx, bx
0x180027b9d  or      ebx, 80070000h
0x180027ba3  test    ebx, ebx
0x180027ba5  jnz     short loc_180027C1F
0x180027ba7  test    edi, edi
0x180027ba9  jz      short loc_180027C0A
0x180027bab  cmp     edi, 1
0x180027bae  jz      short loc_180027BB5
0x180027bb0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180027bb5  mov     ecx, edi
0x180027bb7  shl     rcx, 3; cb
0x180027bbb  call    cs:__imp_CoTaskMemAlloc
0x180027bc1  mov     [r15], rax
0x180027bc4  test    rax, rax
0x180027bc7  jz      short loc_180027C03
0x180027bc9  xor     r8d, r8d
0x180027bcc  mov     [rbp+0], edi
0x180027bcf  test    edi, edi
0x180027bd1  jz      short loc_180027C0F
0x180027bd3  movzx   eax, word ptr [r14+r8*8+6]
0x180027bd9  mov     rcx, [r15]
0x180027bdc  mov     [rcx+r8*8+6], ax
0x180027be2  mov     eax, [r14+r8*8]
0x180027be6  mov     rcx, [r15]
0x180027be9  mov     [rcx+r8*8], eax
0x180027bed  movzx   eax, word ptr [r14+r8*8+4]
0x180027bf3  mov     [rcx+r8*8+4], ax
0x180027bf9  inc     r8d
0x180027bfc  cmp     r8d, edi
0x180027bff  jb      short loc_180027BD3
0x180027c01  jmp     short loc_180027C0F
0x180027c03  mov     ebx, 8007000Eh
0x180027c08  jmp     short loc_180027C0F
0x180027c0a  mov     ebx, 1
0x180027c0f  mov     rcx, r14; pv
0x180027c12  call    cs:__imp_CoTaskMemFree
0x180027c18  jmp     short loc_180027C1F
0x180027c1a  mov     ebx, 80004003h
0x180027c1f  mov     eax, ebx
0x180027c21  add     rsp, 28h
0x180027c25  pop     r15
0x180027c27  pop     r14
0x180027c29  pop     rdi
0x180027c2a  pop     rsi
0x180027c2b  pop     rbp
0x180027c2c  pop     rbx
0x180027c2d  retn
```
