# Queue::~Queue(void)

- ea: `0x1005cbf0`
- end: `0x1005cc90`
- name: `??1Queue@@QAE@XZ`
- size: `160`
- prototype: `void __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1004e3a0`
- `0x10062a00`

## callees

- `0x1005cbf0`
- `0x1005e74d`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1005cc87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1005cc87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1005cc80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1005cc80`

## pseudocode

```c
void __thiscall Queue::~Queue(LPCRITICAL_SECTION lpCriticalSection)
{
  void *v2; // esi
  HANDLE OwningThread; // ecx
  unsigned int v4; // eax
  void **LockCount; // edx
  char *v6; // ecx
  char *v7; // ecx

  while ( lpCriticalSection[1].OwningThread )
  {
    v2 = *(void **)lpCriticalSection[1].LockCount;
    operator delete(v2, 0x18u);
    OwningThread = lpCriticalSection[1].OwningThread;
    if ( OwningThread )
    {
      *(_DWORD *)(lpCriticalSection[1].LockCount + 4 * (_DWORD)OwningThread) = v2;
      v4 = 0;
      LockCount = (void **)lpCriticalSection[1].LockCount;
      if ( *LockCount != v2 )
      {
        do
          ++v4;
        while ( LockCount[v4] != v2 );
      }
      v6 = (char *)lpCriticalSection[1].OwningThread;
      if ( v4 < (unsigned int)v6 )
      {
        v7 = v6 - 1;
        lpCriticalSection[1].OwningThread = v7;
        LockCount[v4] = LockCount[(_DWORD)v7];
      }
    }
  }
  if ( ((int)lpCriticalSection[1].LockSemaphore & 0xFFFFFFFE) != 0 )
  {
    if ( lpCriticalSection[2].LockCount )
      operator delete[]((void *)lpCriticalSection[2].LockCount);
    if ( lpCriticalSection[2].RecursionCount )
      operator delete[]((void *)lpCriticalSection[2].RecursionCount);
  }
  if ( lpCriticalSection[1].LockCount )
    operator delete[]((void *)lpCriticalSection[1].LockCount);
  CloseHandle(lpCriticalSection[1].DebugInfo);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1005cbf0  mov     edi, edi
0x1005cbf2  push    ebx
0x1005cbf3  mov     ebx, ecx
0x1005cbf5  push    edi
0x1005cbf6  cmp     dword ptr [ebx+24h], 0
0x1005cbfa  jbe     short loc_1005CC44
0x1005cbfc  push    esi
0x1005cbfd  nop     dword ptr [eax]
0x1005cc00  mov     eax, [ebx+1Ch]
0x1005cc03  push    18h; unsigned int
0x1005cc05  mov     esi, [eax]
0x1005cc07  push    esi; Block
0x1005cc08  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005cc0d  mov     ecx, [ebx+24h]
0x1005cc10  add     esp, 8
0x1005cc13  test    ecx, ecx
0x1005cc15  jz      short loc_1005CC3D
0x1005cc17  mov     eax, [ebx+1Ch]
0x1005cc1a  mov     [eax+ecx*4], esi
0x1005cc1d  xor     eax, eax
0x1005cc1f  mov     edx, [ebx+1Ch]
0x1005cc22  cmp     [edx], esi
0x1005cc24  jz      short loc_1005CC2C
0x1005cc26  inc     eax
0x1005cc27  cmp     [edx+eax*4], esi
0x1005cc2a  jnz     short loc_1005CC26
0x1005cc2c  mov     ecx, [ebx+24h]
0x1005cc2f  cmp     eax, ecx
0x1005cc31  jnb     short loc_1005CC3D
0x1005cc33  dec     ecx
0x1005cc34  mov     [ebx+24h], ecx
0x1005cc37  mov     ecx, [edx+ecx*4]
0x1005cc3a  mov     [edx+eax*4], ecx
0x1005cc3d  cmp     dword ptr [ebx+24h], 0
0x1005cc41  ja      short loc_1005CC00
0x1005cc43  pop     esi
0x1005cc44  test    dword ptr [ebx+28h], 0FFFFFFFEh
0x1005cc4b  jz      short loc_1005CC6D
0x1005cc4d  mov     eax, [ebx+34h]
0x1005cc50  test    eax, eax
0x1005cc52  jz      short loc_1005CC5D
0x1005cc54  push    eax; Block
0x1005cc55  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005cc5a  add     esp, 4
0x1005cc5d  mov     eax, [ebx+38h]
0x1005cc60  test    eax, eax
0x1005cc62  jz      short loc_1005CC6D
0x1005cc64  push    eax; Block
0x1005cc65  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005cc6a  add     esp, 4
0x1005cc6d  mov     eax, [ebx+1Ch]
0x1005cc70  test    eax, eax
0x1005cc72  jz      short loc_1005CC7D
0x1005cc74  push    eax; Block
0x1005cc75  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005cc7a  add     esp, 4
0x1005cc7d  push    dword ptr [ebx+18h]; hObject
0x1005cc80  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1005cc86  push    ebx; lpCriticalSection
0x1005cc87  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1005cc8d  pop     edi
0x1005cc8e  pop     ebx
0x1005cc8f  retn
```
