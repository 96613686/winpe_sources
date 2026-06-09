# System::Schedule(QMsg *,Err &)

- ea: `0x100614e1`
- end: `0x100615e3`
- name: `?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z`
- size: `258`
- prototype: `void __thiscall(struct QMsg *, struct Err *)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x10056765`
- `0x10057289`
- `0x10060ef7`
- `0x100615f0`
- `0x10074b85`

## callees

- `0x100614e1`
- `0x100619d6`
- `0x10074d41`
- `0x10077a99`
- `0x10077cb4`
- `0x10077d1f`
- `0x10123110`
- `0x10123c5a`
- `0x10123c92`
- `0x10123ca8`
- `0x10123cb3`
- `0x10124048`
- `0x1012410f`
- `0x1012413e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x10061567`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x10061567`

## pseudocode

```c
void __thiscall System::Schedule(struct QMsg *this, struct Err *a2, struct Err *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  Thread *v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // eax
  void *v10; // ebx
  int (__stdcall *v11)(void *); // [esp-4h] [ebp-24h]
  Thread *Block; // [esp+10h] [ebp-10h]

  if ( *((_DWORD *)this + 6) )
    goto LABEL_9;
  v4 = 4 * *((_DWORD *)this + 5);
  if ( !is_mul_ok(4u, *((_DWORD *)this + 5)) )
    v4 = -1;
  v5 = 0;
  *((_DWORD *)this + 6) = operator new[](v4);
  if ( !*((_DWORD *)this + 5) )
  {
LABEL_9:
    if ( !*((_DWORD *)a2 + 2) || Collection::IsMember(*((_DWORD *)this + 21), *((_DWORD *)a2 + 2)) )
      Queue::AddMessage(*((Queue **)this + 7), a2, a3);
    else
      Err::SetError(a3, -1010, v8);
  }
  else
  {
    while ( 1 )
    {
      Block = (Thread *)operator new(4u);
      v6 = Thread::Thread(Block, v11, this, a3);
      v7 = *((_DWORD *)this + 6);
      *(_DWORD *)(v7 + 4 * v5) = v6;
      if ( !*(_DWORD *)(*((_DWORD *)this + 6) + 4 * v5) )
        Err::SetError(a3, -1011, v7);
      if ( (*(_BYTE *)a3 & 8) != 0 )
        break;
      _InterlockedIncrement((volatile signed __int32 *)this + 26);
      ResumeThread(**(HANDLE **)(*((_DWORD *)this + 6) + 4 * v5++));
      if ( v5 >= *((_DWORD *)this + 5) )
        goto LABEL_9;
    }
    v9 = *((_DWORD *)this + 6);
    v10 = *(void **)(v9 + 4 * v5);
    if ( v10 )
    {
      Thread::~Thread(*(Thread **)(v9 + 4 * v5));
      operator delete(v10, 4u);
    }
    *(_DWORD *)(*((_DWORD *)this + 6) + 4 * v5) = 0;
    if ( !v5 )
    {
      operator delete[](*((void **)this + 6));
      *((_DWORD *)this + 6) = 0;
    }
  }
}

```

## disassembly

```asm
0x100614e1  push    4
0x100614e3  mov     eax, offset loc_1012646C
0x100614e8  call    __EH_prolog3
0x100614ed  mov     esi, ecx
0x100614ef  cmp     dword ptr [esi+18h], 0
0x100614f3  mov     ebx, [ebp+arg_4]
0x100614f6  jnz     short loc_10061573
0x100614f8  mov     eax, [esi+14h]
0x100614fb  push    4
0x100614fd  pop     ecx
0x100614fe  mul     ecx
0x10061500  push    0FFFFFFFFh
0x10061502  pop     ecx
0x10061503  cmovb   eax, ecx
0x10061506  push    eax; unsigned int
0x10061507  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1006150c  xor     edi, edi
0x1006150e  mov     [esi+18h], eax
0x10061511  pop     ecx
0x10061512  cmp     [esi+14h], edi
0x10061515  jbe     short loc_10061573
0x10061517  push    4; Size
0x10061519  call    ??2@YAPAXI@Z; operator new(uint)
0x1006151e  pop     ecx
0x1006151f  mov     [ebp+Block], eax
0x10061522  push    ebx; struct Err *
0x10061523  push    esi; lpParameter
0x10061524  push    ecx; int (__stdcall *)(void *)
0x10061525  mov     ecx, eax; this
0x10061527  mov     [ebp+var_4], 0
0x1006152e  call    ??0Thread@@QAE@P6GHPAX@Z0AAVErr@@@Z; Thread::Thread(int (*)(void *),void *,Err &)
0x10061533  mov     [ebp+var_4], 0FFFFFFFFh
0x1006153a  mov     ecx, [esi+18h]
0x1006153d  mov     [ecx+edi*4], eax
0x10061540  mov     eax, [esi+18h]
0x10061543  cmp     dword ptr [eax+edi*4], 0
0x10061547  jnz     short loc_10061556
0x10061549  push    ecx
0x1006154a  push    0FFFFFC0Dh
0x1006154f  mov     ecx, ebx
0x10061551  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10061556  test    byte ptr [ebx], 8
0x10061559  jnz     short loc_1006159A
0x1006155b  lock inc dword ptr [esi+68h]
0x1006155f  mov     eax, [esi+18h]
0x10061562  mov     eax, [eax+edi*4]
0x10061565  push    dword ptr [eax]; hThread
0x10061567  call    ds:__imp__ResumeThread@4; ResumeThread(x)
0x1006156d  inc     edi
0x1006156e  cmp     edi, [esi+14h]
0x10061571  jb      short loc_10061517
0x10061573  mov     edi, [ebp+arg_0]
0x10061576  cmp     dword ptr [edi+8], 0
0x1006157a  jz      short loc_100615D1
0x1006157c  push    dword ptr [edi+8]
0x1006157f  mov     ecx, [esi+54h]
0x10061582  call    ?IsMember@Collection@@QAE?AW4CollBool@@PBX@Z; Collection::IsMember(void const *)
0x10061587  test    eax, eax
0x10061589  jnz     short loc_100615D1
0x1006158b  push    ecx
0x1006158c  push    0FFFFFC0Eh
0x10061591  mov     ecx, ebx
0x10061593  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10061598  jmp     short loc_100615DB
0x1006159a  mov     eax, [esi+18h]
0x1006159d  mov     ebx, [eax+edi*4]
0x100615a0  test    ebx, ebx
0x100615a2  jz      short loc_100615B5
0x100615a4  mov     ecx, ebx; this
0x100615a6  call    ??1Thread@@QAE@XZ; Thread::~Thread(void)
0x100615ab  push    4; unsigned int
0x100615ad  push    ebx; Block
0x100615ae  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100615b3  pop     ecx
0x100615b4  pop     ecx
0x100615b5  mov     eax, [esi+18h]
0x100615b8  mov     dword ptr [eax+edi*4], 0
0x100615bf  test    edi, edi
0x100615c1  jnz     short loc_100615DB
0x100615c3  push    dword ptr [esi+18h]; Block
0x100615c6  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100615cb  pop     ecx
0x100615cc  mov     [esi+18h], edi
0x100615cf  jmp     short loc_100615DB
0x100615d1  mov     ecx, [esi+1Ch]; this
0x100615d4  push    ebx; struct Err *
0x100615d5  push    edi; struct QMsg *
0x100615d6  call    ?AddMessage@Queue@@QAEXPAVQMsg@@AAVErr@@@Z; Queue::AddMessage(QMsg *,Err &)
0x100615db  call    __EH_epilog3
0x100615e0  retn    8
0x1012645a  push    4; unsigned int
0x1012645c  push    [ebp+Block]; Block
0x1012645f  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10126464  pop     ecx
0x10126465  pop     ecx
0x10126466  retn
0x1012646c  nop
0x1012646d  nop
0x1012646e  mov     edx, [esp-4+arg_4]
0x10126472  lea     eax, [edx+0Ch]
0x10126475  mov     ecx, [edx-14h]
0x10126478  xor     ecx, eax; StackCookie
0x1012647a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1012647f  mov     eax, offset stru_10128BCC
0x10126484  jmp     ___CxxFrameHandler3
```
