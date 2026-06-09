# CWSDPublisher::FreeInstanceInfo(ushort const *)

- ea: `0x180002ad0`
- end: `0x180002bb9`
- name: `?FreeInstanceInfo@CWSDPublisher@@IEAAJPEBG@Z`
- size: `233`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003ae8`
- `0x180004498`

## callees

- `0x180001008`
- `0x180001f24`
- `0x180001f70`
- `0x180002a3c`
- `0x180002ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b1e`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::FreeInstanceInfo(CWSDPublisher *this, const unsigned __int16 *a2)
{
  struct INSTANCE_INFO *InstanceInfo; // rax
  struct INSTANCE_INFO *v5; // rsi
  _QWORD *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  bool v10; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  InstanceInfo = CWSDPublisher::FindInstanceInfo(this, a2);
  v5 = InstanceInfo;
  if ( InstanceInfo )
  {
    v6 = (_QWORD *)*((_QWORD *)InstanceInfo + 1);
    v7 = 0;
    v8 = *(_QWORD *)InstanceInfo;
    *v6 = *(_QWORD *)InstanceInfo;
    *(_QWORD *)(v8 + 8) = v6;
    --*((_DWORD *)this + 21);
    operator delete(*((void **)InstanceInfo + 2));
    operator delete(v5);
  }
  else
  {
    v7 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v9 = 0;
  if ( v7 )
    v10 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v10 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v9) = !v10;
    if ( v9 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x180002ad0  push    rbx
0x180002ad2  push    rbp
0x180002ad3  push    rsi
0x180002ad4  push    rdi
0x180002ad5  push    r14
0x180002ad7  sub     rsp, 30h
0x180002adb  mov     rbx, rdx
0x180002ade  mov     rdi, rcx
0x180002ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ae8  lea     r14, WPP_GLOBAL_Control
0x180002aef  cmp     rcx, r14
0x180002af2  jz      short loc_180002B14
0x180002af4  cmp     byte ptr [rcx+19h], 4
0x180002af8  jb      short loc_180002B14
0x180002afa  mov     rcx, [rcx+10h]
0x180002afe  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002b05  mov     edx, 25h ; '%'
0x180002b0a  mov     [rsp+58h+var_38], rdi
0x180002b0f  call    WPP_SF_sq
0x180002b14  lea     rbp, [rdi+88h]
0x180002b1b  mov     rcx, rbp; lpCriticalSection
0x180002b1e  call    cs:__imp_EnterCriticalSection
0x180002b24  mov     rdx, rbx; unsigned __int16 *
0x180002b27  mov     rcx, rdi; this
0x180002b2a  call    ?FindInstanceInfo@CWSDPublisher@@IEAAPEAUINSTANCE_INFO@@PEBG@Z; CWSDPublisher::FindInstanceInfo(ushort const *)
0x180002b2f  mov     rsi, rax
0x180002b32  test    rax, rax
0x180002b35  jz      short loc_180002B5D
0x180002b37  mov     rcx, [rax+8]
0x180002b3b  xor     ebx, ebx
0x180002b3d  mov     rdx, [rax]
0x180002b40  mov     [rcx], rdx
0x180002b43  mov     [rdx+8], rcx
0x180002b47  dec     dword ptr [rdi+54h]
0x180002b4a  mov     rcx, [rax+10h]; Block
0x180002b4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b53  mov     rcx, rsi; Block
0x180002b56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b5b  jmp     short loc_180002B62
0x180002b5d  mov     ebx, 1
0x180002b62  mov     rcx, rbp; lpCriticalSection
0x180002b65  call    cs:__imp_LeaveCriticalSection
0x180002b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b72  xor     eax, eax
0x180002b74  test    ebx, ebx
0x180002b76  jnz     short loc_180002B7E
0x180002b78  cmp     byte ptr [rcx+19h], 4
0x180002b7c  jmp     short loc_180002B82
0x180002b7e  cmp     byte ptr [rcx+19h], 2
0x180002b82  setnb   al
0x180002b85  cmp     rcx, r14
0x180002b88  jz      short loc_180002BAC
0x180002b8a  test    eax, eax
0x180002b8c  jz      short loc_180002BAC
0x180002b8e  mov     rcx, [rcx+10h]
0x180002b92  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002b99  mov     edx, 26h ; '&'
0x180002b9e  mov     [rsp+58h+var_30], ebx
0x180002ba2  mov     [rsp+58h+var_38], rdi
0x180002ba7  call    WPP_SF_sqd
0x180002bac  mov     eax, ebx
0x180002bae  add     rsp, 30h
0x180002bb2  pop     r14
0x180002bb4  pop     rdi
0x180002bb5  pop     rsi
0x180002bb6  pop     rbp
0x180002bb7  pop     rbx
0x180002bb8  retn
```
