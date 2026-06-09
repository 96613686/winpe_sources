# acmStreamClose

- ea: `0x180001f90`
- end: `0x1800021d7`
- name: `acmStreamClose`
- size: `583`
- prototype: `MMRESULT __stdcall(HACMSTREAM has, DWORD fdwClose)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001e60`
- `0x180001f90`
- `0x180003ec0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000206d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000206d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002130`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002130`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000218f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000218f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000213a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000213a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021ab`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x1800020b1`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x1800020b1`

## pseudocode

```c
MMRESULT __stdcall acmStreamClose(HACMSTREAM has, DWORD fdwClose)
{
  __int64 v4; // rcx
  __int64 v5; // rbp
  void *v6; // rsi
  _QWORD *v7; // rax
  __int64 v8; // r10
  MMRESULT v9; // edi
  HDRVR v11; // rcx
  __int64 v12; // rsi
  HACMSTREAM v13; // rcx
  HACMSTREAM v14; // rdx
  __int64 v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rcx

  if ( !(unsigned int)ValidateHandle(has, 3) )
    return 5;
  if ( fdwClose )
    return 10;
  v4 = *((_QWORD *)has + 2);
  v5 = *(_QWORD *)(*(_QWORD *)(v4 + 20) + 4LL);
  if ( v5 != gplag )
    return 5;
  if ( !*((_DWORD *)has + 6) )
    goto LABEL_5;
  if ( *(_QWORD *)(v5 + 112) == v4 )
  {
    *((_DWORD *)has + 6) = 0;
LABEL_5:
    if ( ((_BYTE)has[1] & 2) != 0 )
      v6 = (void *)*((_QWORD *)has + 7);
    else
      v6 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 - 40));
    v7 = (_QWORD *)*((_QWORD *)has + 2);
    if ( v7 )
    {
      v8 = v7[6];
      if ( v8 )
      {
        if ( v8 == -1 )
          v9 = 1;
        else
          v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, HACMSTREAM, _QWORD))v7[6])(
                 v7[7],
                 *(_QWORD *)((char *)v7 + 20),
                 24653,
                 has + 7,
                 0);
LABEL_13:
        if ( !v6 || v9 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)has + 2) - 40LL));
          if ( v9 && *(_QWORD *)(v5 + 112) != *((_QWORD *)has + 2) )
            return v9;
        }
        else
        {
          WaitForSingleObject(v6, 0xFFFFFFFF);
          LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)has + 2) - 40LL));
        }
        if ( v6 )
          CloseHandle(v6);
        v12 = *((_QWORD *)has + 2);
        EnterCriticalSection((LPCRITICAL_SECTION)(v12 - 40));
        v13 = *(HACMSTREAM *)(v12 + 12);
        if ( has == v13 )
        {
          v15 = *((_QWORD *)has + 1);
          v16 = (struct _RTL_CRITICAL_SECTION *)(v12 - 40);
          *(_QWORD *)(v12 + 12) = v15;
          if ( !v15 )
          {
            LeaveCriticalSection(v16);
            if ( ((_DWORD)has[1] & 1) == 0 )
              IDriverClose(*((_QWORD *)has + 2), 0);
            goto LABEL_30;
          }
        }
        else
        {
          if ( !v13 )
            goto LABEL_27;
          do
          {
            v14 = (HACMSTREAM)*((_QWORD *)v13 + 1);
            if ( has == v14 )
              break;
            v13 = (HACMSTREAM)*((_QWORD *)v13 + 1);
          }
          while ( v14 );
          if ( !v13 )
          {
LABEL_27:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v12 - 40));
            return 5;
          }
          *((_QWORD *)v13 + 1) = *((_QWORD *)has + 1);
          v16 = (struct _RTL_CRITICAL_SECTION *)(v12 - 40);
        }
        LeaveCriticalSection(v16);
LABEL_30:
        *(_DWORD *)has = 666;
        DeleteCriticalSection((LPCRITICAL_SECTION)has - 1);
        LocalFree(has - 10);
        return v9;
      }
      v11 = (HDRVR)v7[5];
      if ( v11 )
      {
        v9 = SendDriverMessage(v11, 0x604Du, (LPARAM)(has + 7), 0);
        goto LABEL_13;
      }
    }
    v9 = 5;
    goto LABEL_13;
  }
  return 11;
}

```

## disassembly

```asm
0x180001f90  mov     [rsp+arg_8], rbx
0x180001f95  mov     [rsp+arg_10], rbp
0x180001f9a  push    rdi
0x180001f9b  sub     rsp, 30h
0x180001f9f  mov     edi, edx
0x180001fa1  mov     rbx, rcx
0x180001fa4  mov     edx, 3
0x180001fa9  call    ValidateHandle
0x180001fae  test    eax, eax
0x180001fb0  jz      loc_180002042
0x180001fb6  test    edi, edi
0x180001fb8  jnz     loc_180002153
0x180001fbe  mov     rcx, [rbx+10h]
0x180001fc2  mov     rax, [rcx+14h]
0x180001fc6  mov     rbp, [rax+4]
0x180001fca  cmp     rbp, cs:gplag
0x180001fd1  jnz     short loc_180002042
0x180001fd3  xor     edi, edi
0x180001fd5  cmp     [rbx+18h], edi
0x180001fd8  jnz     loc_18000215D
0x180001fde  test    byte ptr [rbx+4], 2
0x180001fe2  mov     [rsp+38h+arg_0], rsi
0x180001fe7  jz      loc_180002098
0x180001fed  mov     rsi, [rbx+38h]
0x180001ff1  add     rcx, 0FFFFFFFFFFFFFFD8h; lpCriticalSection
0x180001ff5  call    cs:__imp_EnterCriticalSection
0x180001ffb  mov     rax, [rbx+10h]
0x180001fff  test    rax, rax
0x180002002  jz      short loc_180002057
0x180002004  mov     r10, [rax+30h]
0x180002008  lea     r8, [rbx+1Ch]; lParam1
0x18000200c  test    r10, r10
0x18000200f  jz      loc_1800020A0
0x180002015  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180002019  jz      loc_180002175
0x18000201f  mov     rdx, [rax+14h]
0x180002023  mov     r9, r8
0x180002026  mov     rcx, [rax+38h]
0x18000202a  mov     r8d, 604Dh
0x180002030  mov     rax, r10
0x180002033  mov     [rsp+38h+var_18], rdi
0x180002038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203d  mov     rdi, rax
0x180002040  jmp     short loc_18000205C
0x180002042  mov     eax, 5
0x180002047  mov     rbx, [rsp+38h+arg_8]
0x18000204c  mov     rbp, [rsp+38h+arg_10]
0x180002051  add     rsp, 30h
0x180002055  pop     rdi
0x180002056  retn
0x180002057  mov     edi, 5
0x18000205c  test    rsi, rsi
0x18000205f  jnz     loc_18000217F
0x180002065  mov     rcx, [rbx+10h]
0x180002069  sub     rcx, 28h ; '('; lpCriticalSection
0x18000206d  call    cs:__imp_LeaveCriticalSection
0x180002073  test    edi, edi
0x180002075  jz      short loc_1800020BC
0x180002077  mov     rax, [rbx+10h]
0x18000207b  cmp     [rbp+70h], rax
0x18000207f  jz      short loc_1800020BC
0x180002081  mov     eax, edi
0x180002083  mov     rsi, [rsp+38h+arg_0]
0x180002088  mov     rbx, [rsp+38h+arg_8]
0x18000208d  mov     rbp, [rsp+38h+arg_10]
0x180002092  add     rsp, 30h
0x180002096  pop     rdi
0x180002097  retn
0x180002098  mov     rsi, rdi
0x18000209b  jmp     loc_180001FF1
0x1800020a0  mov     rcx, [rax+28h]; hDriver
0x1800020a4  test    rcx, rcx
0x1800020a7  jz      short loc_180002057
0x1800020a9  xor     r9d, r9d; lParam2
0x1800020ac  mov     edx, 604Dh; message
0x1800020b1  call    cs:__imp_SendDriverMessage
0x1800020b7  mov     rdi, rax
0x1800020ba  jmp     short loc_18000205C
0x1800020bc  test    rsi, rsi
0x1800020bf  jnz     loc_1800021A8
0x1800020c5  mov     rsi, [rbx+10h]
0x1800020c9  lea     rcx, [rsi-28h]; lpCriticalSection
0x1800020cd  call    cs:__imp_EnterCriticalSection
0x1800020d3  mov     rcx, [rsi+0Ch]
0x1800020d7  cmp     rbx, rcx
0x1800020da  jz      short loc_18000210B
0x1800020dc  test    rcx, rcx
0x1800020df  jz      short loc_1800020F7
0x1800020e1  mov     rdx, [rcx+8]
0x1800020e5  cmp     rbx, rdx
0x1800020e8  jz      short loc_1800020F2
0x1800020ea  mov     rcx, rdx
0x1800020ed  test    rdx, rdx
0x1800020f0  jnz     short loc_1800020E1
0x1800020f2  test    rcx, rcx
0x1800020f5  jnz     short loc_180002145
0x1800020f7  lea     rcx, [rsi-28h]; lpCriticalSection
0x1800020fb  call    cs:__imp_LeaveCriticalSection
0x180002101  mov     eax, 5
0x180002106  jmp     loc_180002083
0x18000210b  mov     rax, [rbx+8]
0x18000210f  lea     rcx, [rsi-28h]; lpCriticalSection
0x180002113  mov     [rsi+0Ch], rax
0x180002117  test    rax, rax
0x18000211a  jz      loc_1800021B6
0x180002120  call    cs:__imp_LeaveCriticalSection
0x180002126  lea     rcx, [rbx-28h]; lpCriticalSection
0x18000212a  mov     dword ptr [rbx], 29Ah
0x180002130  call    cs:__imp_DeleteCriticalSection
0x180002136  lea     rcx, [rbx-28h]; hMem
0x18000213a  call    cs:__imp_LocalFree
0x180002140  jmp     loc_180002081
0x180002145  mov     rax, [rbx+8]
0x180002149  mov     [rcx+8], rax
0x18000214d  lea     rcx, [rsi-28h]
0x180002151  jmp     short loc_180002120
0x180002153  mov     eax, 0Ah
0x180002158  jmp     loc_180002088
0x18000215d  cmp     [rbp+70h], rcx
0x180002161  jz      short loc_18000216D
0x180002163  mov     eax, 0Bh
0x180002168  jmp     loc_180002088
0x18000216d  mov     [rbx+18h], edi
0x180002170  jmp     loc_180001FDE
0x180002175  mov     edi, 1
0x18000217a  jmp     loc_18000205C
0x18000217f  test    edi, edi
0x180002181  jnz     loc_180002065
0x180002187  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000218c  mov     rcx, rsi; hHandle
0x18000218f  call    cs:__imp_WaitForSingleObject
0x180002195  mov     rcx, [rbx+10h]
0x180002199  sub     rcx, 28h ; '('; lpCriticalSection
0x18000219d  call    cs:__imp_LeaveCriticalSection
0x1800021a3  jmp     loc_1800020BC
0x1800021a8  mov     rcx, rsi; hObject
0x1800021ab  call    cs:__imp_CloseHandle
0x1800021b1  jmp     loc_1800020C5
0x1800021b6  call    cs:__imp_LeaveCriticalSection
0x1800021bc  mov     eax, [rbx+4]
0x1800021bf  test    al, 1
0x1800021c1  jnz     loc_180002126
0x1800021c7  mov     rcx, [rbx+10h]
0x1800021cb  xor     edx, edx
0x1800021cd  call    IDriverClose
0x1800021d2  jmp     loc_180002126
```
