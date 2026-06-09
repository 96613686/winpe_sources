# QuicTimerWheelUpdateConnection

- ea: `0x14000f400`
- end: `0x14000f657`
- name: `QuicTimerWheelUpdateConnection`
- size: `599`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000edc0`
- `0x140016210`
- `0x1400211bc`
- `0x14002b8e8`

## callees

- `0x14000da60`
- `0x14000f400`
- `0x14001d7d0`
- `0x14003c8e0`
- `0x14003ead8`
- `0x140049a98`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000f493`
- `ntoskrnl!_snprintf_s` at `0x14000f595`
- `ntoskrnl!_snprintf_s` at `0x14000f5f0`
- `ntoskrnl!_snprintf_s` at `0x14000f493`
- `ntoskrnl!_snprintf_s` at `0x14000f595`
- `ntoskrnl!_snprintf_s` at `0x14000f5f0`

## pseudocode

```c
void __fastcall QuicTimerWheelUpdateConnection(unsigned __int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  __int64 *v3; // r9
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 *i; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v2 = *(_QWORD *)(a2 + 1368);
  v3 = (__int64 *)(a2 + 48);
  v6 = *(_QWORD *)(a2 + 48);
  if ( v6 )
  {
    v7 = *(_QWORD **)(a2 + 56);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    if ( v2 == -1 || (*(_BYTE *)(a2 + 249) & 1) != 0 )
    {
      *v3 = 0;
      if ( byte_14005C48E < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[time][%p] Removing Connection %p.", a1, (const void *)a2);
        McTemplateU0s_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)QuicLogVerbose, DstBuf);
      }
      if ( a2 == a1[2] )
        QuicTimerWheelUpdate(a1);
      QuicConnRelease(a2, 4);
      --a1[1];
      return;
    }
  }
  else
  {
    if ( v2 == -1 || (*(_BYTE *)(a2 + 249) & 1) != 0 )
      return;
    ++a1[1];
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 240));
  }
  v9 = (v2 / 0x3E8 * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
  v10 = a1[4] + 16 * (((v9 + ((v2 / 0x3E8 - v9) >> 1)) >> 9) % *((unsigned int *)a1 + 6));
  for ( i = *(__int64 **)(v10 + 8); i != (__int64 *)v10; i = (__int64 *)i[1] )
  {
    if ( v2 > i[165] )
      break;
  }
  v12 = *i;
  *v3 = *i;
  v3[1] = (__int64)i;
  *(_QWORD *)(v12 + 8) = v3;
  *i = (__int64)v3;
  if ( byte_14005C48E < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[time][%p] Updating Connection %p.", a1, (const void *)a2);
    McTemplateU0s_EtwWriteTransfer(v13, (const EVENT_DESCRIPTOR *)QuicLogVerbose, DstBuf);
  }
  if ( v2 >= *a1 )
  {
    if ( a2 == a1[2] )
      QuicTimerWheelUpdate(a1);
  }
  else
  {
    *a1 = v2;
    a1[2] = a2;
    if ( byte_14005C48E < 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[time][%p] Next Expiration = {%llu, %p}.",
        a1,
        v2,
        (const void *)a2);
      McTemplateU0s_EtwWriteTransfer(v14, (const EVENT_DESCRIPTOR *)QuicLogVerbose, DstBuf);
    }
  }
  if ( a1[1] > (unsigned int)(32 * *((_DWORD *)a1 + 6)) )
    QuicTimerWheelResize(a1);
}

```

## disassembly

```asm
0x14000f400  mov     [rsp+arg_10], rbx
0x14000f405  mov     [rsp+arg_18], rsi
0x14000f40a  push    rdi
0x14000f40b  sub     rsp, 0D0h
0x14000f412  mov     rax, cs:__security_cookie
0x14000f419  xor     rax, rsp
0x14000f41c  mov     [rsp+0D8h+var_18], rax
0x14000f424  mov     rsi, [rdx+558h]
0x14000f42b  lea     r9, [rdx+30h]
0x14000f42f  mov     rbx, rcx
0x14000f432  mov     rdi, rdx
0x14000f435  mov     rcx, [r9]
0x14000f438  test    rcx, rcx
0x14000f43b  jz      loc_14000F4D4
0x14000f441  mov     rax, [rdx+38h]
0x14000f445  mov     [rax], rcx
0x14000f448  mov     [rcx+8], rax
0x14000f44c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000f450  jz      short loc_14000F45F
0x14000f452  test    byte ptr [rdx+0F9h], 1
0x14000f459  jz      loc_14000F4F6
0x14000f45f  mov     qword ptr [r9], 0
0x14000f466  movzx   eax, cs:byte_14005C48E
0x14000f46d  test    al, al
0x14000f46f  jns     short loc_14000F4B0
0x14000f471  mov     [rsp+0D8h+var_B0], rdi
0x14000f476  lea     r9, aTimePRemovingC; "[time][%p] Removing Connection %p."
0x14000f47d  mov     edx, 80h; SizeInBytes
0x14000f482  mov     [rsp+0D8h+var_B8], rbx
0x14000f487  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000f48e  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000f493  call    cs:__imp__snprintf_s
0x14000f49a  nop     dword ptr [rax+rax+00h]
0x14000f49f  lea     r8, [rsp+0D8h+DstBuf]
0x14000f4a4  lea     rdx, QuicLogVerbose
0x14000f4ab  call    McTemplateU0s_EtwWriteTransfer
0x14000f4b0  cmp     rdi, [rbx+10h]
0x14000f4b4  jnz     short loc_14000F4BE
0x14000f4b6  mov     rcx, rbx
0x14000f4b9  call    QuicTimerWheelUpdate
0x14000f4be  mov     edx, 4
0x14000f4c3  mov     rcx, rdi
0x14000f4c6  call    QuicConnRelease
0x14000f4cb  dec     qword ptr [rbx+8]
0x14000f4cf  jmp     loc_14000F631
0x14000f4d4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000f4d8  jz      loc_14000F631
0x14000f4de  test    byte ptr [rdx+0F9h], 1
0x14000f4e5  jnz     loc_14000F631
0x14000f4eb  inc     qword ptr [rbx+8]
0x14000f4ef  lock inc dword ptr [rdx+0F0h]
0x14000f4f6  mov     rcx, 624DD2F1A9FBE77h
0x14000f500  mov     r8, rsi
0x14000f503  mov     rax, rcx
0x14000f506  mul     rsi
0x14000f509  mov     rax, rcx
0x14000f50c  mov     ecx, [rbx+18h]
0x14000f50f  sub     r8, rdx
0x14000f512  shr     r8, 1
0x14000f515  add     r8, rdx
0x14000f518  shr     r8, 9
0x14000f51c  mul     r8
0x14000f51f  sub     r8, rdx
0x14000f522  shr     r8, 1
0x14000f525  lea     rax, [rdx+r8]
0x14000f529  xor     edx, edx
0x14000f52b  shr     rax, 9
0x14000f52f  div     rcx
0x14000f532  mov     ecx, edx
0x14000f534  shl     rcx, 4
0x14000f538  add     rcx, [rbx+20h]
0x14000f53c  mov     rax, [rcx+8]
0x14000f540  cmp     rax, rcx
0x14000f543  jz      short loc_14000F557
0x14000f545  cmp     rsi, [rax+528h]
0x14000f54c  ja      short loc_14000F557
0x14000f54e  mov     rax, [rax+8]
0x14000f552  cmp     rax, rcx
0x14000f555  jnz     short loc_14000F545
0x14000f557  mov     rcx, [rax]
0x14000f55a  mov     [r9], rcx
0x14000f55d  mov     [r9+8], rax
0x14000f561  mov     [rcx+8], r9
0x14000f565  mov     [rax], r9
0x14000f568  movzx   eax, cs:byte_14005C48E
0x14000f56f  test    al, al
0x14000f571  jns     short loc_14000F5B2
0x14000f573  mov     [rsp+0D8h+var_B0], rdi
0x14000f578  lea     r9, aTimePUpdatingC; "[time][%p] Updating Connection %p."
0x14000f57f  mov     edx, 80h; SizeInBytes
0x14000f584  mov     [rsp+0D8h+var_B8], rbx
0x14000f589  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000f590  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000f595  call    cs:__imp__snprintf_s
0x14000f59c  nop     dword ptr [rax+rax+00h]
0x14000f5a1  lea     r8, [rsp+0D8h+DstBuf]
0x14000f5a6  lea     rdx, QuicLogVerbose
0x14000f5ad  call    McTemplateU0s_EtwWriteTransfer
0x14000f5b2  cmp     rsi, [rbx]
0x14000f5b5  jnb     short loc_14000F60F
0x14000f5b7  mov     [rbx], rsi
0x14000f5ba  mov     [rbx+10h], rdi
0x14000f5be  movzx   eax, cs:byte_14005C48E
0x14000f5c5  test    al, al
0x14000f5c7  jns     short loc_14000F61D
0x14000f5c9  mov     [rsp+0D8h+var_A8], rdi
0x14000f5ce  lea     r9, aTimePNextExpir_0; "[time][%p] Next Expiration = {%llu, %p}"...
0x14000f5d5  mov     [rsp+0D8h+var_B0], rsi
0x14000f5da  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000f5df  mov     edx, 80h; SizeInBytes
0x14000f5e4  mov     [rsp+0D8h+var_B8], rbx
0x14000f5e9  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000f5f0  call    cs:__imp__snprintf_s
0x14000f5f7  nop     dword ptr [rax+rax+00h]
0x14000f5fc  lea     r8, [rsp+0D8h+DstBuf]
0x14000f601  lea     rdx, QuicLogVerbose
0x14000f608  call    McTemplateU0s_EtwWriteTransfer
0x14000f60d  jmp     short loc_14000F61D
0x14000f60f  cmp     rdi, [rbx+10h]
0x14000f613  jnz     short loc_14000F61D
0x14000f615  mov     rcx, rbx
0x14000f618  call    QuicTimerWheelUpdate
0x14000f61d  mov     eax, [rbx+18h]
0x14000f620  shl     eax, 5
0x14000f623  cmp     [rbx+8], rax
0x14000f627  jbe     short loc_14000F631
0x14000f629  mov     rcx, rbx
0x14000f62c  call    QuicTimerWheelResize
0x14000f631  mov     rcx, [rsp+0D8h+var_18]
0x14000f639  xor     rcx, rsp; StackCookie
0x14000f63c  call    __security_check_cookie
0x14000f641  lea     r11, [rsp+0D8h+var_8]
0x14000f649  mov     rbx, [r11+20h]
0x14000f64d  mov     rsi, [r11+28h]
0x14000f651  mov     rsp, r11
0x14000f654  pop     rdi
0x14000f655  retn
```
