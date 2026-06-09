# QuicLibraryGetBinding

- ea: `0x140004460`
- end: `0x140004726`
- name: `QuicLibraryGetBinding`
- size: `710`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140001d6c`
- `0x140002840`
- `0x140003fac`

## callees

- `0x140002e8c`
- `0x140004460`
- `0x140004730`
- `0x140020880`
- `0x140028714`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140004619`
- `ntoskrnl!_snprintf_s` at `0x140004619`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000454d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000466b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000454d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000466b`

## string_xrefs

- `0x140004528`: `Binding already in use`
- `0x1400046c1`: `Binding already in use`

## pseudocode

```c
__int64 __fastcall QuicLibraryGetBinding(_QWORD *a1, __int64 *a2)
{
  char v4; // r14
  int v5; // r15d
  bool v6; // bp
  int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  char v11; // al
  __int128 *v12; // rcx
  __int128 v13; // xmm0
  __int64 v14; // xmm1_8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int128 v27; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v28; // [rsp+30h] [rbp-C8h]
  __int64 v29; // [rsp+38h] [rbp-C0h]
  char DstBuf[128]; // [rsp+40h] [rbp-B8h] BYREF

  if ( !*a1 || (v4 = 0, !__ROR2__(*(_WORD *)(*a1 + 2LL), 8)) )
    v4 = 1;
  v5 = a1[2] & 2;
  v6 = (a1[2] & 4) != 0;
  if ( v4 )
    goto LABEL_14;
  v7 = -1073741275;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = QuicLibraryLookupBinding(*((unsigned int *)a1 + 10), *a1, a1[1]);
  v10 = v8;
  if ( v8 )
  {
    if ( v5 && (v11 = *(_BYTE *)(v8 + 16), (v11 & 1) == 0) && v6 == ((v11 & 2) != 0) )
    {
      ++*(_DWORD *)(v10 + 20);
      v7 = 0;
      *a2 = v10;
    }
    else
    {
      if ( (byte_14005C48D & 0x20) != 0 )
        McTemplateU0ps_EtwWriteTransfer(v9, QuicBindingError, v10, "Binding already in use");
      v7 = -1073741302;
    }
  }
  KeReleaseSpinLock(&SpinLock, NewIrql);
  if ( v7 == -1073741275 )
  {
LABEL_14:
    v7 = QuicBindingInitialize((__int64)a1, a2);
    if ( v7 >= 0 )
    {
      v12 = *(__int128 **)(*a2 + 32);
      v13 = *v12;
      v14 = *((_QWORD *)v12 + 2);
      LODWORD(v29) = *((_DWORD *)v12 + 6);
      v27 = v13;
      v28 = v14;
      NewIrql = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( (QuicLibraryGetDatapathFeatures(v16, v15, v17, v18) & 8) != 0 )
        v19 = a1[1];
      else
        v19 = 0;
      v20 = QuicLibraryLookupBinding(*((unsigned int *)a1 + 10), &v27, v19);
      v21 = v20;
      if ( v20 )
      {
        if ( !v4 && (*(_BYTE *)(v20 + 16) & 1) == 0 )
          ++*(_DWORD *)(v20 + 20);
      }
      else
      {
        if ( (__int64 *)qword_14005C5A8 == &qword_14005C5A8 )
        {
          if ( (byte_14005C48E & 0x40) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Now in use.", v27, v28, v29);
            McTemplateU0s_EtwWriteTransfer(v22, QuicLogInfo, DstBuf);
          }
          byte_14005C491 = 1;
        }
        ++*(_DWORD *)(*a2 + 20);
        v23 = (_QWORD *)*a2;
        v24 = (_QWORD *)qword_14005C5B0;
        *v23 = &qword_14005C5A8;
        v23[1] = v24;
        *v24 = v23;
        qword_14005C5B0 = (__int64)v23;
      }
      KeReleaseSpinLock(&SpinLock, NewIrql);
      if ( v21 )
      {
        if ( v4 )
        {
          if ( (byte_14005C48D & 0x20) != 0 )
            McTemplateU0ps_EtwWriteTransfer(v25, QuicBindingError, *a2, "Binding ephemeral port reuse encountered");
          QuicBindingUninitialize((PVOID)*a2);
          *a2 = 0;
          return (unsigned int)-1071382525;
        }
        else if ( (*(_BYTE *)(v21 + 16) & 1) != 0 )
        {
          if ( (byte_14005C48D & 0x20) != 0 )
            McTemplateU0ps_EtwWriteTransfer(v25, QuicBindingError, v21, "Binding already in use");
          QuicBindingUninitialize((PVOID)*a2);
          *a2 = 0;
          return (unsigned int)-1073741302;
        }
        else
        {
          QuicBindingUninitialize((PVOID)*a2);
          *a2 = v21;
          return 0;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140004460  mov     [rsp+arg_10], rbx
0x140004465  mov     [rsp+arg_18], rbp
0x14000446a  push    rsi
0x14000446b  push    rdi
0x14000446c  push    r12
0x14000446e  push    r14
0x140004470  push    r15
0x140004472  sub     rsp, 0D0h
0x140004479  mov     rax, cs:__security_cookie
0x140004480  xor     rax, rsp
0x140004483  mov     [rsp+0F8h+var_38], rax
0x14000448b  mov     rax, [rcx]
0x14000448e  xor     r12d, r12d
0x140004491  mov     rbx, rdx
0x140004494  mov     rsi, rcx
0x140004497  test    rax, rax
0x14000449a  jz      short loc_1400044AC
0x14000449c  movzx   eax, word ptr [rax+2]
0x1400044a0  mov     r14b, r12b
0x1400044a3  ror     ax, 8
0x1400044a7  test    ax, ax
0x1400044aa  jnz     short loc_1400044AF
0x1400044ac  mov     r14b, 1
0x1400044af  mov     ebp, [rcx+10h]
0x1400044b2  mov     r15d, ebp
0x1400044b5  shr     ebp, 2
0x1400044b8  and     r15d, 2
0x1400044bc  and     bpl, 1
0x1400044c0  test    r14b, r14b
0x1400044c3  jnz     loc_140004565
0x1400044c9  lea     rcx, SpinLock; SpinLock
0x1400044d0  mov     edi, 0C0000225h
0x1400044d5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400044dc  nop     dword ptr [rax+rax+00h]
0x1400044e1  mov     cs:NewIrql, al
0x1400044e7  mov     r8, [rsi+8]
0x1400044eb  mov     rdx, [rsi]
0x1400044ee  mov     ecx, [rsi+28h]
0x1400044f1  call    QuicLibraryLookupBinding
0x1400044f6  mov     r8, rax
0x1400044f9  test    rax, rax
0x1400044fc  jz      short loc_140004540
0x1400044fe  test    r15d, r15d
0x140004501  jz      short loc_14000451F
0x140004503  mov     al, [rax+10h]
0x140004506  test    al, 1
0x140004508  jnz     short loc_14000451F
0x14000450a  shr     al, 1
0x14000450c  and     al, 1
0x14000450e  cmp     bpl, al
0x140004511  jnz     short loc_14000451F
0x140004513  inc     dword ptr [r8+14h]
0x140004517  mov     edi, r12d
0x14000451a  mov     [rbx], r8
0x14000451d  jmp     short loc_140004540
0x14000451f  test    cs:byte_14005C48D, 20h
0x140004526  jz      short loc_14000453B
0x140004528  lea     r9, aBindingAlready; "Binding already in use"
0x14000452f  lea     rdx, QuicBindingError
0x140004536  call    McTemplateU0ps_EtwWriteTransfer
0x14000453b  mov     edi, 0C000020Ah
0x140004540  mov     dl, cs:NewIrql; NewIrql
0x140004546  lea     rcx, SpinLock; SpinLock
0x14000454d  call    cs:__imp_KeReleaseSpinLock
0x140004554  nop     dword ptr [rax+rax+00h]
0x140004559  cmp     edi, 0C0000225h
0x14000455f  jnz     loc_1400046F7
0x140004565  mov     rdx, rbx
0x140004568  mov     rcx, rsi
0x14000456b  call    QuicBindingInitialize
0x140004570  mov     edi, eax
0x140004572  test    eax, eax
0x140004574  js      loc_1400046F7
0x14000457a  mov     rcx, [rbx]
0x14000457d  mov     rcx, [rcx+20h]
0x140004581  movups  xmm0, xmmword ptr [rcx]
0x140004584  movsd   xmm1, qword ptr [rcx+10h]
0x140004589  mov     ecx, [rcx+18h]
0x14000458c  mov     dword ptr [rsp+0F8h+var_C0], ecx
0x140004590  lea     rcx, SpinLock; SpinLock
0x140004597  movups  [rsp+0F8h+var_D8], xmm0
0x14000459c  movsd   [rsp+0F8h+var_C8], xmm1
0x1400045a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400045a9  nop     dword ptr [rax+rax+00h]
0x1400045ae  mov     cs:NewIrql, al
0x1400045b4  call    QuicLibraryGetDatapathFeatures
0x1400045b9  test    al, 8
0x1400045bb  jz      short loc_1400045C3
0x1400045bd  mov     r8, [rsi+8]
0x1400045c1  jmp     short loc_1400045C6
0x1400045c3  mov     r8, r12
0x1400045c6  mov     ecx, [rsi+28h]
0x1400045c9  lea     rdx, [rsp+0F8h+var_D8]
0x1400045ce  call    QuicLibraryLookupBinding
0x1400045d3  mov     rsi, rax
0x1400045d6  test    rax, rax
0x1400045d9  jz      short loc_1400045EB
0x1400045db  test    r14b, r14b
0x1400045de  jnz     short loc_14000465E
0x1400045e0  test    byte ptr [rax+10h], 1
0x1400045e4  jnz     short loc_14000465E
0x1400045e6  inc     dword ptr [rax+14h]
0x1400045e9  jmp     short loc_14000465E
0x1400045eb  lea     rbp, qword_14005C5A8
0x1400045f2  cmp     cs:qword_14005C5A8, rbp
0x1400045f9  jnz     short loc_14000463D
0x1400045fb  test    cs:byte_14005C48E, 40h
0x140004602  jz      short loc_140004636
0x140004604  lea     r9, aLibNowInUse; "[ lib] Now in use."
0x14000460b  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000460f  mov     edx, 80h; SizeInBytes
0x140004614  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x140004619  call    cs:__imp__snprintf_s
0x140004620  nop     dword ptr [rax+rax+00h]
0x140004625  lea     r8, [rsp+0F8h+DstBuf]
0x14000462a  lea     rdx, QuicLogInfo
0x140004631  call    McTemplateU0s_EtwWriteTransfer
0x140004636  mov     cs:byte_14005C491, 1
0x14000463d  mov     rax, [rbx]
0x140004640  inc     dword ptr [rax+14h]
0x140004643  mov     rdx, [rbx]
0x140004646  mov     rax, cs:qword_14005C5B0
0x14000464d  mov     [rdx], rbp
0x140004650  mov     [rdx+8], rax
0x140004654  mov     [rax], rdx
0x140004657  mov     cs:qword_14005C5B0, rdx
0x14000465e  mov     dl, cs:NewIrql; NewIrql
0x140004664  lea     rcx, SpinLock; SpinLock
0x14000466b  call    cs:__imp_KeReleaseSpinLock
0x140004672  nop     dword ptr [rax+rax+00h]
0x140004677  test    rsi, rsi
0x14000467a  jz      short loc_1400046F7
0x14000467c  test    r14b, r14b
0x14000467f  jz      short loc_1400046B2
0x140004681  test    cs:byte_14005C48D, 20h
0x140004688  jz      short loc_1400046A0
0x14000468a  mov     r8, [rbx]
0x14000468d  lea     r9, aBindingEphemer; "Binding ephemeral port reuse encountere"...
0x140004694  lea     rdx, QuicBindingError
0x14000469b  call    McTemplateU0ps_EtwWriteTransfer
0x1400046a0  mov     rcx, [rbx]; P
0x1400046a3  call    QuicBindingUninitialize
0x1400046a8  mov     [rbx], r12
0x1400046ab  mov     edi, 0C0240003h
0x1400046b0  jmp     short loc_1400046F7
0x1400046b2  test    byte ptr [rsi+10h], 1
0x1400046b6  jz      short loc_1400046E9
0x1400046b8  test    cs:byte_14005C48D, 20h
0x1400046bf  jz      short loc_1400046D7
0x1400046c1  lea     r9, aBindingAlready; "Binding already in use"
0x1400046c8  mov     r8, rsi
0x1400046cb  lea     rdx, QuicBindingError
0x1400046d2  call    McTemplateU0ps_EtwWriteTransfer
0x1400046d7  mov     rcx, [rbx]; P
0x1400046da  call    QuicBindingUninitialize
0x1400046df  mov     [rbx], r12
0x1400046e2  mov     edi, 0C000020Ah
0x1400046e7  jmp     short loc_1400046F7
0x1400046e9  mov     rcx, [rbx]; P
0x1400046ec  call    QuicBindingUninitialize
0x1400046f1  mov     [rbx], rsi
0x1400046f4  mov     edi, r12d
0x1400046f7  mov     eax, edi
0x1400046f9  mov     rcx, [rsp+0F8h+var_38]
0x140004701  xor     rcx, rsp; StackCookie
0x140004704  call    __security_check_cookie
0x140004709  lea     r11, [rsp+0F8h+var_28]
0x140004711  mov     rbx, [r11+40h]
0x140004715  mov     rbp, [r11+48h]
0x140004719  mov     rsp, r11
0x14000471c  pop     r15
0x14000471e  pop     r14
0x140004720  pop     r12
0x140004722  pop     rdi
0x140004723  pop     rsi
0x140004724  retn
```
