# Kd1394Connection::Write(ulong,void *,ulong,ulong *)

- ea: `0x180437650`
- end: `0x18043787f`
- name: `?Write@Kd1394Connection@@UEAAJKPEAXKPEAK@Z`
- size: `559`
- prototype: `int(Kd1394Connection *__hidden this, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800b94c4`
- `0x1800db3fc`
- `0x180431fe0`
- `0x180437650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804376dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804376f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804377ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804376dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804376f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804377ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180437859`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804376c8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180437783`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804376c8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180437783`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437723`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437835`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437723`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180437835`

## pseudocode

```c
__int64 __fastcall Kd1394Connection::Write(
        Kd1394Connection *this,
        int a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesWritten)
{
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // edi
  unsigned int v13; // ebx
  void *v14; // rcx
  unsigned int v15; // esi
  signed int LastError; // eax
  signed int v17; // eax
  void *v18; // rcx
  unsigned int v19; // eax
  signed int v20; // eax
  signed int v21; // eax

  if ( (a2 & 0xFFFFFFFC) != 0 )
    return 2147942487LL;
  result = Kd1394Connection::SwitchVirtualDebuggerDriverMode((Kd1394Connection *)((char *)this - 16), 0);
  if ( !(_DWORD)result )
  {
    v12 = -2147024890;
    v13 = -2147467259;
    *lpNumberOfBytesWritten = 0;
    v14 = (void *)*((_QWORD *)this + 4);
    if ( v14 )
    {
      v15 = 0;
      if ( !WriteFile(v14, a3, a4, lpNumberOfBytesWritten, (LPOVERLAPPED)((char *)this + 104)) )
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
          if ( v15 == -2147023899 )
          {
            if ( !GetOverlappedResult(
                    *((HANDLE *)this + 4),
                    (LPOVERLAPPED)((char *)this + 104),
                    lpNumberOfBytesWritten,
                    1) )
            {
              if ( GetLastError() )
              {
                v17 = GetLastError();
                v13 = v17;
                if ( v17 > 0 )
                  return (unsigned __int16)v17 | 0x80070000;
              }
              return v13;
            }
            v15 = 0;
          }
        }
        else
        {
          v15 = -2147467259;
        }
      }
    }
    else
    {
      v15 = -2147024890;
    }
    v18 = (void *)*((_QWORD *)this + 80);
    if ( !v18 )
      goto LABEL_22;
    v12 = 0;
    if ( WriteFile(v18, a3, a4, lpNumberOfBytesWritten, (LPOVERLAPPED)((char *)this + 104)) )
      goto LABEL_22;
    if ( !GetLastError() )
    {
      v12 = -2147467259;
      goto LABEL_22;
    }
    v20 = GetLastError();
    v12 = v20;
    if ( v20 > 0 )
      v12 = (unsigned __int16)v20 | 0x80070000;
    if ( v12 != -2147023899 )
    {
LABEL_22:
      if ( v12 )
        v12 = v15;
      if ( v12 )
        return v12;
      goto LABEL_25;
    }
    if ( GetOverlappedResult(*((HANDLE *)this + 80), (LPOVERLAPPED)((char *)this + 104), lpNumberOfBytesWritten, 1) )
    {
      v12 = 0;
LABEL_25:
      if ( (*((_BYTE *)this + 56) & 2) != 0 )
      {
        if ( *lpNumberOfBytesWritten > a4 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v18, v9, v10, v11);
        v19 = a4;
        if ( *lpNumberOfBytesWritten < a4 )
          v19 = *lpNumberOfBytesWritten;
        *lpNumberOfBytesWritten = v19;
        KdConnection::OutputIo((KdConnection *)v18, L"1394: Wrote %d bytes of %d\n", a3, a4, v19);
      }
      *((_QWORD *)this + 20) += *lpNumberOfBytesWritten;
      return v12;
    }
    if ( GetLastError() )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        return (unsigned __int16)v21 | 0x80070000;
      return (unsigned int)v21;
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180437650  push    rbx
0x180437652  push    rbp
0x180437653  push    rsi
0x180437654  push    rdi
0x180437655  push    r12
0x180437657  push    r13
0x180437659  push    r14
0x18043765b  push    r15
0x18043765d  sub     rsp, 38h
0x180437661  mov     r15d, r9d
0x180437664  mov     r13, r8
0x180437667  mov     rbp, rcx
0x18043766a  test    edx, 0FFFFFFFCh
0x180437670  jz      short loc_18043767C
0x180437672  mov     eax, 80070057h
0x180437677  jmp     loc_1804377ED
0x18043767c  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180437680  xor     edx, edx; unsigned int
0x180437682  call    ?SwitchVirtualDebuggerDriverMode@Kd1394Connection@@QEAAJK@Z; Kd1394Connection::SwitchVirtualDebuggerDriverMode(ulong)
0x180437687  test    eax, eax
0x180437689  jnz     loc_1804377ED
0x18043768f  mov     r14, [rsp+78h+lpNumberOfBytesWritten]
0x180437697  lea     r12, [rbp+68h]
0x18043769b  mov     edi, 80070006h
0x1804376a0  mov     ebx, 80004005h
0x1804376a5  mov     [r14], eax
0x1804376a8  mov     rcx, [rbp+20h]; hFile
0x1804376ac  test    rcx, rcx
0x1804376af  jnz     short loc_1804376B8
0x1804376b1  mov     esi, edi
0x1804376b3  jmp     loc_180437767
0x1804376b8  mov     r9, r14; lpNumberOfBytesWritten
0x1804376bb  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x1804376c0  mov     r8d, r15d; nNumberOfBytesToWrite
0x1804376c3  mov     rdx, r13; lpBuffer
0x1804376c6  xor     esi, esi
0x1804376c8  call    cs:__imp_WriteFile
0x1804376cf  nop     dword ptr [rax+rax+00h]
0x1804376d4  test    eax, eax
0x1804376d6  jnz     loc_180437767
0x1804376dc  call    cs:__imp_GetLastError
0x1804376e3  nop     dword ptr [rax+rax+00h]
0x1804376e8  test    eax, eax
0x1804376ea  jnz     short loc_1804376F0
0x1804376ec  mov     esi, ebx
0x1804376ee  jmp     short loc_180437767
0x1804376f0  call    cs:__imp_GetLastError
0x1804376f7  nop     dword ptr [rax+rax+00h]
0x1804376fc  mov     esi, eax
0x1804376fe  test    eax, eax
0x180437700  jle     short loc_18043770B
0x180437702  movzx   esi, ax
0x180437705  or      esi, 80070000h
0x18043770b  cmp     esi, 800703E5h
0x180437711  jnz     short loc_180437767
0x180437713  mov     rcx, [rbp+20h]; hFile
0x180437717  mov     r9d, 1; bWait
0x18043771d  mov     r8, r14; lpNumberOfBytesTransferred
0x180437720  mov     rdx, r12; lpOverlapped
0x180437723  call    cs:__imp_GetOverlappedResult
0x18043772a  nop     dword ptr [rax+rax+00h]
0x18043772f  test    eax, eax
0x180437731  jnz     short loc_180437765
0x180437733  call    cs:__imp_GetLastError
0x18043773a  nop     dword ptr [rax+rax+00h]
0x18043773f  test    eax, eax
0x180437741  jz      short loc_18043775E
0x180437743  call    cs:__imp_GetLastError
0x18043774a  nop     dword ptr [rax+rax+00h]
0x18043774f  mov     ebx, eax
0x180437751  test    eax, eax
0x180437753  jle     short loc_18043775E
0x180437755  movzx   ebx, ax
0x180437758  or      ebx, 80070000h
0x18043775e  mov     eax, ebx
0x180437760  jmp     loc_1804377ED
0x180437765  xor     esi, esi
0x180437767  mov     rcx, [rbp+280h]; hFile
0x18043776e  test    rcx, rcx
0x180437771  jz      short loc_1804377A5
0x180437773  mov     r9, r14; lpNumberOfBytesWritten
0x180437776  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x18043777b  mov     r8d, r15d; nNumberOfBytesToWrite
0x18043777e  mov     rdx, r13; lpBuffer
0x180437781  xor     edi, edi
0x180437783  call    cs:__imp_WriteFile
0x18043778a  nop     dword ptr [rax+rax+00h]
0x18043778f  test    eax, eax
0x180437791  jnz     short loc_1804377A5
0x180437793  call    cs:__imp_GetLastError
0x18043779a  nop     dword ptr [rax+rax+00h]
0x18043779f  test    eax, eax
0x1804377a1  jnz     short loc_1804377FF
0x1804377a3  mov     edi, ebx
0x1804377a5  test    edi, edi
0x1804377a7  cmovnz  edi, esi
0x1804377aa  test    edi, edi
0x1804377ac  jnz     short loc_1804377EB
0x1804377ae  test    byte ptr [rbp+38h], 2
0x1804377b2  jz      short loc_1804377E1
0x1804377b4  cmp     [r14], r15d
0x1804377b7  jbe     short loc_1804377BE
0x1804377b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1804377be  cmp     [r14], r15d
0x1804377c1  lea     rdx, a1394WroteDByte; "1394: Wrote %d bytes of %d\n"
0x1804377c8  mov     eax, r15d
0x1804377cb  mov     r9d, r15d; unsigned int
0x1804377ce  cmovb   eax, [r14]
0x1804377d2  mov     r8, r13; void *
0x1804377d5  mov     [r14], eax
0x1804377d8  mov     dword ptr [rsp+78h+lpOverlapped], eax; unsigned int
0x1804377dc  call    ?OutputIo@KdConnection@@QEAAXPEAGPEAXKK@Z; KdConnection::OutputIo(ushort *,void *,ulong,ulong)
0x1804377e1  mov     eax, [r14]
0x1804377e4  add     [rbp+0A0h], rax
0x1804377eb  mov     eax, edi
0x1804377ed  add     rsp, 38h
0x1804377f1  pop     r15
0x1804377f3  pop     r14
0x1804377f5  pop     r13
0x1804377f7  pop     r12
0x1804377f9  pop     rdi
0x1804377fa  pop     rsi
0x1804377fb  pop     rbp
0x1804377fc  pop     rbx
0x1804377fd  retn
0x1804377ff  call    cs:__imp_GetLastError
0x180437806  nop     dword ptr [rax+rax+00h]
0x18043780b  mov     edi, eax
0x18043780d  test    eax, eax
0x18043780f  jle     short loc_18043781A
0x180437811  movzx   edi, ax
0x180437814  or      edi, 80070000h
0x18043781a  cmp     edi, 800703E5h
0x180437820  jnz     short loc_1804377A5
0x180437822  mov     rcx, [rbp+280h]; hFile
0x180437829  mov     r9d, 1; bWait
0x18043782f  mov     r8, r14; lpNumberOfBytesTransferred
0x180437832  mov     rdx, r12; lpOverlapped
0x180437835  call    cs:__imp_GetOverlappedResult
0x18043783c  nop     dword ptr [rax+rax+00h]
0x180437841  test    eax, eax
0x180437843  jnz     short loc_180437878
0x180437845  call    cs:__imp_GetLastError
0x18043784c  nop     dword ptr [rax+rax+00h]
0x180437851  test    eax, eax
0x180437853  jz      loc_18043775E
0x180437859  call    cs:__imp_GetLastError
0x180437860  nop     dword ptr [rax+rax+00h]
0x180437865  test    eax, eax
0x180437867  jle     short loc_180437871
0x180437869  movzx   eax, ax
0x18043786c  or      eax, 80070000h
0x180437871  mov     ebx, eax
0x180437873  jmp     loc_18043775E
0x180437878  xor     edi, edi
0x18043787a  jmp     loc_1804377AE
```
