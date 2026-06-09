# Win32LiveSystemProvider::GetThreadContextEx(void *,void *,void *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong,bool)

- ea: `0x180013790`
- end: `0x18001392b`
- name: `?GetThreadContextEx@Win32LiveSystemProvider@@UEAAJPEAX00KPEA_K11K_N@Z`
- size: `411`
- prototype: `unsigned int __fastcall(Win32LiveSystemProvider *this, void *, void *, void *, unsigned int Size, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180013730`
- `0x180024c90`

## callees

- `0x1800020ae`
- `0x1800020ba`
- `0x1800021f4`
- `0x180003424`
- `0x180013790`
- `0x180013ae4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001388c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001388c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013886`

## pseudocode

```c
unsigned int __fastcall Win32LiveSystemProvider::GetThreadContextEx(
        Win32LiveSystemProvider *this,
        void *a2,
        void *a3,
        void *a4,
        unsigned int Size,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned int a9)
{
  void *v12; // rax
  signed int LastError; // eax
  unsigned int v14; // ebx
  _QWORD *v16; // rbx
  unsigned __int64 *v17; // [rsp+30h] [rbp-38h]
  void *Block[3]; // [rsp+40h] [rbp-28h] BYREF
  char v19; // [rsp+58h] [rbp-10h]

  Block[1] = (void *)-2LL;
  if ( Size <= 0x4D0 )
  {
    v12 = o__aligned_malloc_0(0x4D0u, 0x10u);
    Block[0] = v12;
    if ( v12 )
    {
      Block[2] = Block;
      v19 = 1;
      memset_0(v12, 0, 0x4D0u);
      *((_DWORD *)Block[0] + 12) = 1048607;
      if ( *(&g_Kernel32CallsMdwd + 1) )
      {
        if ( (unsigned int)(*(&g_Kernel32CallsMdwd + 1))(a3, Block[0]) )
        {
          v16 = Block[0];
          memcpy_0(a4, Block[0], Size);
          *a6 = v16[31];
          *a7 = v16[19];
          if ( v16 )
            aligned_free(v16);
          return 0;
        }
        else
        {
          if ( GetLastError() )
          {
            LastError = GetLastError();
            v14 = LastError;
            if ( LastError > 0 )
              v14 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v14 = -2147467259;
          }
          if ( Block[0] )
            aligned_free(Block[0]);
          return v14;
        }
      }
      else
      {
        if ( Block[0] )
          aligned_free(Block[0]);
        return -2147467263;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  else if ( (a9 & 0x200000) != 0 )
  {
    return Win32LiveSystemProvider::GetXStateContext(this, a3, a4, Size, a6, a7, v17);
  }
  else
  {
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180013790  mov     r11, rsp
0x180013793  push    rdi
0x180013794  sub     rsp, 60h
0x180013798  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x1800137a0  mov     [r11+8], rbx
0x1800137a4  mov     [r11+10h], rsi
0x1800137a8  mov     rsi, r9
0x1800137ab  mov     rdi, r8
0x1800137ae  mov     ebx, dword ptr [rsp+68h+Size]
0x1800137b5  cmp     ebx, 4D0h
0x1800137bb  jbe     short loc_1800137FF
0x1800137bd  test    [rsp+68h+arg_40], 200000h
0x1800137c8  jz      short loc_1800137F5
0x1800137ca  mov     rax, [rsp+68h+arg_30]
0x1800137d2  mov     [r11-40h], rax
0x1800137d6  mov     rax, [rsp+68h+arg_28]
0x1800137de  mov     [r11-48h], rax
0x1800137e2  mov     r9d, ebx; unsigned int
0x1800137e5  mov     r8, rsi; void *
0x1800137e8  mov     rdx, rdi; void *
0x1800137eb  call    ?GetXStateContext@Win32LiveSystemProvider@@AEAAJPEAX0KPEA_K11@Z; Win32LiveSystemProvider::GetXStateContext(void *,void *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x1800137f0  jmp     loc_18001391B
0x1800137f5  mov     eax, 80070057h
0x1800137fa  jmp     loc_18001391B
0x1800137ff  mov     edx, 10h; Alignment
0x180013804  mov     ecx, 4D0h; Size
0x180013809  call    _o__aligned_malloc_0
0x18001380e  mov     [rsp+68h+Block], rax
0x180013813  test    rax, rax
0x180013816  jnz     short loc_180013822
0x180013818  mov     eax, 8007000Eh
0x18001381d  jmp     loc_18001391B
0x180013822  lea     rcx, [rsp+68h+Block]
0x180013827  mov     [rsp+68h+var_18], rcx
0x18001382c  mov     [rsp+68h+var_10], 1
0x180013831  xor     edx, edx; Val
0x180013833  mov     r8d, 4D0h; Size
0x180013839  mov     rcx, rax; void *
0x18001383c  call    memset_0
0x180013841  mov     rax, [rsp+68h+Block]
0x180013846  mov     dword ptr [rax+30h], 10001Fh
0x18001384d  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180013854  test    rax, rax
0x180013857  jnz     short loc_180013872
0x180013859  mov     rcx, [rsp+68h+Block]; Block
0x18001385e  test    rcx, rcx
0x180013861  jz      short loc_180013868
0x180013863  call    _aligned_free
0x180013868  mov     eax, 80004001h
0x18001386d  jmp     loc_18001391B
0x180013872  mov     rdx, [rsp+68h+Block]
0x180013877  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x18001387e  test    rax, rax
0x180013881  jnz     short loc_1800138AD
0x180013883  lea     ecx, [rax+32h]; dwErrCode
0x180013886  call    cs:__imp_SetLastError
0x18001388c  call    cs:__imp_GetLastError
0x180013892  test    eax, eax
0x180013894  jz      short loc_180013905
0x180013896  call    cs:__imp_GetLastError
0x18001389c  mov     ebx, eax
0x18001389e  test    eax, eax
0x1800138a0  jle     short loc_18001390A
0x1800138a2  movzx   ebx, ax
0x1800138a5  or      ebx, 80070000h
0x1800138ab  jmp     short loc_18001390A
0x1800138ad  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1800138b4  mov     rcx, rdi
0x1800138b7  call    rax
0x1800138b9  test    eax, eax
0x1800138bb  jz      short loc_18001388C
0x1800138bd  mov     r8, rbx; Size
0x1800138c0  mov     rbx, [rsp+68h+Block]
0x1800138c5  mov     rdx, rbx; Src
0x1800138c8  mov     rcx, rsi; void *
0x1800138cb  call    memcpy_0
0x1800138d0  mov     rdx, [rbx+0F8h]
0x1800138d7  mov     rax, [rsp+68h+arg_28]
0x1800138df  mov     [rax], rdx
0x1800138e2  mov     rdx, [rbx+98h]
0x1800138e9  mov     rax, [rsp+68h+arg_30]
0x1800138f1  mov     [rax], rdx
0x1800138f4  test    rbx, rbx
0x1800138f7  jz      short loc_180013901
0x1800138f9  mov     rcx, rbx; Block
0x1800138fc  call    _aligned_free
0x180013901  xor     eax, eax
0x180013903  jmp     short loc_18001391B
0x180013905  mov     ebx, 80004005h
0x18001390a  mov     rcx, [rsp+68h+Block]; Block
0x18001390f  test    rcx, rcx
0x180013912  jz      short loc_180013919
0x180013914  call    _aligned_free
0x180013919  mov     eax, ebx
0x18001391b  mov     rbx, [rsp+68h+arg_0]
0x180013920  mov     rsi, [rsp+68h+arg_8]
0x180013925  add     rsp, 60h
0x180013929  pop     rdi
0x18001392a  retn
```
