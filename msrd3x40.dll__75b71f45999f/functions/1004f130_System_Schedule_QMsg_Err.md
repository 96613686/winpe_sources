# System::Schedule(QMsg *,Err &)

- ea: `0x1004f130`
- end: `0x1004f39c`
- name: `?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z`
- size: `620`
- prototype: `void __thiscall(struct QMsg *lpParameter, struct Err *)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10018b80`
- `0x10018e10`
- `0x10024450`
- `0x10049bf0`
- `0x1004e980`
- `0x1004f3b0`

## callees

- `0x1000f750`
- `0x10025ee0`
- `0x1004eda0`
- `0x1004f130`
- `0x1005cca0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1004f32d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1004f32d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1004f1b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1004f1b7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1004f2ab`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1004f2ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1004f1c6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1004f1c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004f335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004f335`

## pseudocode

```c
void __thiscall System::Schedule(struct QMsg *lpParameter, struct Err *a2, struct Err *a3)
{
  unsigned int v4; // eax
  bool v5; // zf
  _DWORD *v6; // ebx
  HANDLE Thread; // eax
  struct Err *v8; // ecx
  int v9; // ecx
  int v10; // ebx
  int v11; // edx
  unsigned int v12; // ecx
  int v13; // eax
  HANDLE *v14; // esi
  DWORD ThreadId[2]; // [esp+38h] [ebp-18h] BYREF
  int v16; // [esp+40h] [ebp-10h]
  int v17; // [esp+4Ch] [ebp-4h]

  if ( *((_DWORD *)lpParameter + 6) )
    goto LABEL_25;
  v4 = 4 * *((_DWORD *)lpParameter + 5);
  if ( !is_mul_ok(4u, *((_DWORD *)lpParameter + 5)) )
    v4 = -1;
  *((_DWORD *)lpParameter + 6) = operator new[](v4);
  v5 = *((_DWORD *)lpParameter + 5) == 0;
  v16 = 0;
  if ( v5 )
  {
LABEL_25:
    v11 = *((_DWORD *)a2 + 2);
    if ( v11 )
    {
      v12 = *((_DWORD *)lpParameter + 43);
      v13 = 0;
      if ( v12 )
      {
        while ( *(_DWORD *)(*((_DWORD *)lpParameter + 41) + 4 * v13) != v11 )
        {
          if ( ++v13 >= v12 )
            goto LABEL_29;
        }
      }
      else
      {
LABEL_29:
        if ( v13 == v12 )
        {
          Err::SetError(a3, -1010, *((_DWORD *)lpParameter + 43));
          return;
        }
      }
    }
    Queue::AddMessage((LPCRITICAL_SECTION)((char *)lpParameter + 28), a2, a3);
  }
  else
  {
    while ( 1 )
    {
      v6 = operator new(4u);
      ThreadId[1] = (DWORD)v6;
      Thread = CreateThread(0, 0, System::WorkerThread, lpParameter, 4u, ThreadId);
      *v6 = Thread;
      if ( Thread )
      {
        SetThreadPriority(Thread, 1);
      }
      else
      {
        System::ErrGetLastError(v8);
        if ( (*(_DWORD *)a3 & 1) == 0 && *((_DWORD *)a3 + 1) == -5500 )
        {
          if ( (*(_DWORD *)a3 & 0xFFFFFFFE) != 0 )
          {
            if ( *((_DWORD *)a3 + 3) )
              operator delete[](*((void **)a3 + 3));
            if ( *((_DWORD *)a3 + 4) )
              operator delete[](*((void **)a3 + 4));
          }
          *(_DWORD *)a3 = 8;
          *((_DWORD *)a3 + 1) = -5500;
          *((_DWORD *)a3 + 2) = -8400;
          *((_DWORD *)a3 + 3) = 0;
          *((_DWORD *)a3 + 4) = 0;
        }
      }
      v9 = v16;
      v17 = -1;
      *(_DWORD *)(*((_DWORD *)lpParameter + 6) + 4 * v16) = v6;
      v10 = v9;
      if ( !*(_DWORD *)(*((_DWORD *)lpParameter + 6) + 4 * v9) && *(int *)a3 < 8 )
      {
        if ( (*(_DWORD *)a3 & 0xFFFFFFFE) != 0 )
        {
          if ( *((_DWORD *)a3 + 3) )
            operator delete[](*((void **)a3 + 3));
          if ( *((_DWORD *)a3 + 4) )
            operator delete[](*((void **)a3 + 4));
        }
        *(_DWORD *)a3 = 8;
        *((_DWORD *)a3 + 1) = -1011;
        *((_DWORD *)a3 + 2) = 0;
        *((_DWORD *)a3 + 3) = 0;
        *((_DWORD *)a3 + 4) = 0;
      }
      if ( (*(_BYTE *)a3 & 8) != 0 )
        break;
      _InterlockedIncrement((volatile signed __int32 *)lpParameter + 53);
      ResumeThread(**(HANDLE **)(*((_DWORD *)lpParameter + 6) + 4 * v10));
      v16 = v10 + 1;
      if ( (unsigned int)(v10 + 1) >= *((_DWORD *)lpParameter + 5) )
        goto LABEL_25;
    }
    v14 = *(HANDLE **)(*((_DWORD *)lpParameter + 6) + 4 * v10);
    if ( v14 )
    {
      if ( *v14 )
      {
        WaitForSingleObject(*v14, 0x3E8u);
        CloseHandle(*v14);
        *v14 = 0;
      }
      operator delete(v14, 4u);
    }
    *(_DWORD *)(*((_DWORD *)lpParameter + 6) + 4 * v10) = 0;
    if ( !v10 )
    {
      operator delete[](*((void **)lpParameter + 6));
      *((_DWORD *)lpParameter + 6) = 0;
    }
  }
}

```

## disassembly

```asm
0x1004f130  mov     edi, edi
0x1004f132  push    ebp
0x1004f133  mov     ebp, esp
0x1004f135  push    0FFFFFFFFh
0x1004f137  push    offset ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z_SEH
0x1004f13c  mov     eax, large fs:0
0x1004f142  push    eax
0x1004f143  sub     esp, 34h
0x1004f146  push    ebx
0x1004f147  push    esi
0x1004f148  push    edi
0x1004f149  mov     eax, ___security_cookie
0x1004f14e  xor     eax, ebp
0x1004f150  push    eax
0x1004f151  lea     eax, [ebp+var_C]
0x1004f154  mov     large fs:0, eax
0x1004f15a  mov     edi, ecx
0x1004f15c  cmp     dword ptr [edi+18h], 0
0x1004f160  mov     esi, [ebp+arg_4]
0x1004f163  jnz     loc_1004F2BE
0x1004f169  mov     eax, [edi+14h]
0x1004f16c  mov     ecx, 4
0x1004f171  mul     ecx
0x1004f173  mov     ecx, 0FFFFFFFFh
0x1004f178  cmovb   eax, ecx
0x1004f17b  push    eax; unsigned int
0x1004f17c  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004f181  add     esp, 4
0x1004f184  mov     [edi+18h], eax
0x1004f187  cmp     dword ptr [edi+14h], 0
0x1004f18b  mov     [ebp+var_10], 0
0x1004f192  jbe     loc_1004F2BE
0x1004f198  push    4; Size
0x1004f19a  call    ??2@YAPAXI@Z; operator new(uint)
0x1004f19f  mov     ebx, eax
0x1004f1a1  add     esp, 4
0x1004f1a4  mov     [ebp+Block], ebx
0x1004f1a7  lea     eax, [ebp+ThreadId]
0x1004f1aa  push    eax; lpThreadId
0x1004f1ab  push    4; dwCreationFlags
0x1004f1ad  push    edi; lpParameter
0x1004f1ae  push    offset ?WorkerThread@System@@CGHPAX@Z; lpStartAddress
0x1004f1b3  push    0; dwStackSize
0x1004f1b5  push    0; lpThreadAttributes
0x1004f1b7  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x1004f1bd  mov     [ebx], eax
0x1004f1bf  test    eax, eax
0x1004f1c1  jz      short loc_1004F1CE
0x1004f1c3  push    1; nPriority
0x1004f1c5  push    eax; hThread
0x1004f1c6  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x1004f1cc  jmp     short loc_1004F22C
0x1004f1ce  push    esi
0x1004f1cf  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004f1d4  mov     eax, [esi]
0x1004f1d6  test    al, 1
0x1004f1d8  jnz     short loc_1004F22C
0x1004f1da  cmp     dword ptr [esi+4], 0FFFFEA84h
0x1004f1e1  jnz     short loc_1004F22C
0x1004f1e3  test    eax, 0FFFFFFFEh
0x1004f1e8  jz      short loc_1004F20A
0x1004f1ea  mov     eax, [esi+0Ch]
0x1004f1ed  test    eax, eax
0x1004f1ef  jz      short loc_1004F1FA
0x1004f1f1  push    eax; Block
0x1004f1f2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f1f7  add     esp, 4
0x1004f1fa  mov     eax, [esi+10h]
0x1004f1fd  test    eax, eax
0x1004f1ff  jz      short loc_1004F20A
0x1004f201  push    eax; Block
0x1004f202  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f207  add     esp, 4
0x1004f20a  mov     dword ptr [esi], 8
0x1004f210  mov     dword ptr [esi+4], 0FFFFEA84h
0x1004f217  mov     dword ptr [esi+8], 0FFFFDF30h
0x1004f21e  mov     dword ptr [esi+0Ch], 0
0x1004f225  mov     dword ptr [esi+10h], 0
0x1004f22c  mov     ecx, [ebp+var_10]
0x1004f22f  mov     [ebp+var_4], 0FFFFFFFFh
0x1004f236  mov     eax, [edi+18h]
0x1004f239  mov     [eax+ecx*4], ebx
0x1004f23c  mov     ebx, ecx
0x1004f23e  mov     eax, [edi+18h]
0x1004f241  cmp     dword ptr [eax+ebx*4], 0
0x1004f245  jnz     short loc_1004F297
0x1004f247  mov     eax, [esi]
0x1004f249  cmp     eax, 8
0x1004f24c  jge     short loc_1004F297
0x1004f24e  test    eax, 0FFFFFFFEh
0x1004f253  jz      short loc_1004F275
0x1004f255  mov     eax, [esi+0Ch]
0x1004f258  test    eax, eax
0x1004f25a  jz      short loc_1004F265
0x1004f25c  push    eax; Block
0x1004f25d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f262  add     esp, 4
0x1004f265  mov     eax, [esi+10h]
0x1004f268  test    eax, eax
0x1004f26a  jz      short loc_1004F275
0x1004f26c  push    eax; Block
0x1004f26d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f272  add     esp, 4
0x1004f275  mov     dword ptr [esi], 8
0x1004f27b  mov     dword ptr [esi+4], 0FFFFFC0Dh
0x1004f282  mov     dword ptr [esi+8], 0
0x1004f289  mov     dword ptr [esi+0Ch], 0
0x1004f290  mov     dword ptr [esi+10h], 0
0x1004f297  test    byte ptr [esi], 8
0x1004f29a  jnz     short loc_1004F317
0x1004f29c  lock inc dword ptr [edi+0D4h]
0x1004f2a3  mov     eax, [edi+18h]
0x1004f2a6  mov     eax, [eax+ebx*4]
0x1004f2a9  push    dword ptr [eax]; hThread
0x1004f2ab  call    ds:__imp__ResumeThread@4; ResumeThread(x)
0x1004f2b1  inc     ebx
0x1004f2b2  mov     [ebp+var_10], ebx
0x1004f2b5  cmp     ebx, [edi+14h]
0x1004f2b8  jb      loc_1004F198
0x1004f2be  mov     edx, [ebp+arg_0]
0x1004f2c1  mov     edx, [edx+8]
0x1004f2c4  test    edx, edx
0x1004f2c6  jz      loc_1004F37C
0x1004f2cc  mov     ecx, [edi+0ACh]
0x1004f2d2  xor     eax, eax
0x1004f2d4  test    ecx, ecx
0x1004f2d6  jz      short loc_1004F2EE
0x1004f2d8  mov     ebx, [edi+0A4h]
0x1004f2de  mov     edi, edi
0x1004f2e0  cmp     [ebx+eax*4], edx
0x1004f2e3  jz      loc_1004F37C
0x1004f2e9  inc     eax
0x1004f2ea  cmp     eax, ecx
0x1004f2ec  jb      short loc_1004F2E0
0x1004f2ee  cmp     eax, ecx
0x1004f2f0  jnz     loc_1004F37C
0x1004f2f6  push    ecx
0x1004f2f7  push    0FFFFFC0Eh
0x1004f2fc  mov     ecx, esi
0x1004f2fe  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004f303  mov     ecx, [ebp+var_C]
0x1004f306  mov     large fs:0, ecx
0x1004f30d  pop     ecx
0x1004f30e  pop     edi
0x1004f30f  pop     esi
0x1004f310  pop     ebx
0x1004f311  mov     esp, ebp
0x1004f313  pop     ebp
0x1004f314  retn    8
0x1004f317  mov     eax, [edi+18h]
0x1004f31a  mov     esi, [eax+ebx*4]
0x1004f31d  test    esi, esi
0x1004f31f  jz      short loc_1004F34C
0x1004f321  mov     eax, [esi]
0x1004f323  test    eax, eax
0x1004f325  jz      short loc_1004F341
0x1004f327  push    3E8h; dwMilliseconds
0x1004f32c  push    eax; hHandle
0x1004f32d  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1004f333  push    dword ptr [esi]; hObject
0x1004f335  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1004f33b  mov     dword ptr [esi], 0
0x1004f341  push    4; unsigned int
0x1004f343  push    esi; Block
0x1004f344  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1004f349  add     esp, 8
0x1004f34c  mov     eax, [edi+18h]
0x1004f34f  mov     dword ptr [eax+ebx*4], 0
0x1004f356  test    ebx, ebx
0x1004f358  jnz     short loc_1004F388
0x1004f35a  push    dword ptr [edi+18h]; Block
0x1004f35d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f362  add     esp, 4
0x1004f365  mov     [edi+18h], ebx
0x1004f368  mov     ecx, [ebp+var_C]
0x1004f36b  mov     large fs:0, ecx
0x1004f372  pop     ecx
0x1004f373  pop     edi
0x1004f374  pop     esi
0x1004f375  pop     ebx
0x1004f376  mov     esp, ebp
0x1004f378  pop     ebp
0x1004f379  retn    8
0x1004f37c  push    esi; struct Err *
0x1004f37d  push    [ebp+arg_0]; struct QMsg *
0x1004f380  lea     ecx, [edi+1Ch]; lpCriticalSection
0x1004f383  call    ?AddMessage@Queue@@QAEXPAVQMsg@@AAVErr@@@Z; Queue::AddMessage(QMsg *,Err &)
0x1004f388  mov     ecx, [ebp+var_C]
0x1004f38b  mov     large fs:0, ecx
0x1004f392  pop     ecx
0x1004f393  pop     edi
0x1004f394  pop     esi
0x1004f395  pop     ebx
0x1004f396  mov     esp, ebp
0x1004f398  pop     ebp
0x1004f399  retn    8
0x10061840  push    4; unsigned int
0x10061842  mov     eax, [ebp+Block]
0x10061845  push    eax; Block
0x10061846  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006184b  add     esp, 8
0x1006184e  retn
0x1006184f  lea     ecx, [ebp+var_2C]; this
0x10061852  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061857  lea     ecx, [ebp+var_40]; this
0x1006185a  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061864  nop
0x10061865  nop
0x10061866  mov     edx, [esp-4+arg_4]
0x1006186a  lea     eax, [edx+0Ch]
0x1006186d  mov     ecx, [edx-44h]
0x10061870  xor     ecx, eax; StackCookie
0x10061872  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061877  mov     eax, offset stru_1006417C
0x1006187c  jmp     ___CxxFrameHandler3
```
