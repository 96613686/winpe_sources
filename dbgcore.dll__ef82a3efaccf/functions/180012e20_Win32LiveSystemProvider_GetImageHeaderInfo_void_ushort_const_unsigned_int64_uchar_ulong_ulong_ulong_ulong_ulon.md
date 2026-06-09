# Win32LiveSystemProvider::GetImageHeaderInfo(void *,ushort const *,unsigned __int64,uchar *,ulong *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x180012e20`
- end: `0x180013012`
- name: `?GetImageHeaderInfo@Win32LiveSystemProvider@@UEAAJPEAXPEBG_KPEAEPEAK4444@Z`
- size: `498`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, void *, const unsigned __int16 *, unsigned __int64, unsigned __int8 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180012e20`
- `0x180026cb4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::GetImageHeaderInfo(
        Win32LiveSystemProvider *this,
        void *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9,
        unsigned int *a10)
{
  __int64 result; // rax
  int v14; // ebx
  char *v15; // rdi
  int v16; // ebx
  struct _IMAGE_NT_HEADERS *v17; // rbx
  unsigned __int8 v18; // al
  DWORD VirtualAddress; // eax
  _BYTE v22[60]; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+8Ch] [rbp-74h]
  _IMAGE_NT_HEADERS64 v24; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v22, 0, 0x40u);
  result = (*(__int64 (__fastcall **)(Win32LiveSystemProvider *, void *, __int64, _BYTE *, int))(*(_QWORD *)this + 240LL))(
             this,
             a2,
             a4,
             v22,
             64);
  if ( !(_DWORD)result )
  {
    v14 = v23 + 264;
    v15 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(
                    *((_QWORD *)this + 6),
                    (unsigned int)(v23 + 264));
    if ( !v15 )
      return 2147942414LL;
    v16 = (*(__int64 (__fastcall **)(Win32LiveSystemProvider *, void *, __int64, char *, int))(*(_QWORD *)this + 240LL))(
            this,
            a2,
            a4,
            v15,
            v14);
    if ( v16 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v15);
      return (unsigned int)v16;
    }
    memset_0(&v24, 0, sizeof(v24));
    v17 = GenImageNtHeader(v15, &v24);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v15);
    if ( !v17 )
      return 2147943554LL;
    *a6 = v24.FileHeader.Machine;
    *a7 = v24.OptionalHeader.SizeOfImage;
    *a8 = v24.OptionalHeader.CheckSum;
    *a9 = v24.FileHeader.TimeDateStamp;
    if ( v24.OptionalHeader.Magic == 267 )
    {
      v18 = 4;
    }
    else
    {
      if ( v24.OptionalHeader.Magic != 523 )
      {
        *a5 = 0;
        return 3489661051LL;
      }
      v18 = 8;
    }
    *a5 = v18;
    if ( v24.OptionalHeader.NumberOfRvaAndSizes > 9 && v24.OptionalHeader.DataDirectory[9].Size )
      VirtualAddress = v24.OptionalHeader.DataDirectory[9].VirtualAddress;
    else
      VirtualAddress = 0;
    *a10 = VirtualAddress;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012e20  mov     [rsp-8+arg_10], rbx
0x180012e25  push    rbp
0x180012e26  push    rsi
0x180012e27  push    rdi
0x180012e28  push    r12
0x180012e2a  push    r13
0x180012e2c  push    r14
0x180012e2e  push    r15
0x180012e30  lea     rbp, [rsp-0B0h]
0x180012e38  sub     rsp, 1B0h
0x180012e3f  mov     rax, cs:__security_cookie
0x180012e46  xor     rax, rsp
0x180012e49  mov     [rbp+0E0h+var_40], rax
0x180012e50  mov     rax, [rbp+0E0h+arg_38]
0x180012e57  mov     rbx, rdx
0x180012e5a  mov     r14, [rbp+0E0h+arg_20]
0x180012e61  mov     rsi, rcx
0x180012e64  mov     r12, [rbp+0E0h+arg_28]
0x180012e6b  lea     rcx, [rsp+1E0h+var_190]; void *
0x180012e70  mov     r13, [rbp+0E0h+arg_30]
0x180012e77  mov     rdi, r9
0x180012e7a  mov     r15, [rbp+0E0h+arg_48]
0x180012e81  mov     [rsp+1E0h+var_1A8], rdx
0x180012e86  xor     edx, edx; Val
0x180012e88  mov     [rsp+1E0h+var_1A0], rax
0x180012e8d  mov     rax, [rbp+0E0h+arg_40]
0x180012e94  mov     [rsp+1E0h+var_1B0], r9
0x180012e99  lea     r8d, [rdx+40h]; Size
0x180012e9d  mov     [rsp+1E0h+var_198], rax
0x180012ea2  call    memset_0
0x180012ea7  mov     rax, [rsi]
0x180012eaa  lea     r9, [rsp+1E0h+var_190]
0x180012eaf  mov     r8, rdi
0x180012eb2  mov     [rsp+1E0h+var_1C0], 40h ; '@'
0x180012eba  mov     rdx, rbx
0x180012ebd  mov     rcx, rsi
0x180012ec0  mov     rax, [rax+0F0h]
0x180012ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ecc  test    eax, eax
0x180012ece  jnz     loc_180012FE8
0x180012ed4  mov     rcx, [rsi+30h]
0x180012ed8  mov     ebx, [rbp+0E0h+var_154]
0x180012edb  add     ebx, 108h
0x180012ee1  mov     edx, ebx
0x180012ee3  mov     rax, [rcx]
0x180012ee6  mov     rax, [rax+8]
0x180012eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eef  mov     rdi, rax
0x180012ef2  test    rax, rax
0x180012ef5  jnz     short loc_180012F01
0x180012ef7  mov     eax, 8007000Eh
0x180012efc  jmp     loc_180012FE8
0x180012f01  mov     rax, [rsi]
0x180012f04  mov     r9, rdi
0x180012f07  mov     r8, [rsp+1E0h+var_1B0]
0x180012f0c  mov     rcx, rsi
0x180012f0f  mov     rdx, [rsp+1E0h+var_1A8]
0x180012f14  mov     [rsp+1E0h+var_1C0], ebx
0x180012f18  mov     rax, [rax+0F0h]
0x180012f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f24  mov     ebx, eax
0x180012f26  test    eax, eax
0x180012f28  jns     short loc_180012F44
0x180012f2a  mov     rcx, [rsi+30h]
0x180012f2e  mov     rdx, [rcx]
0x180012f31  mov     rax, [rdx+18h]
0x180012f35  mov     rdx, rdi
0x180012f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f3d  mov     eax, ebx
0x180012f3f  jmp     loc_180012FE8
0x180012f44  xor     edx, edx; Val
0x180012f46  lea     rcx, [rbp+0E0h+var_150]; void *
0x180012f4a  mov     r8d, 108h; Size
0x180012f50  call    memset_0
0x180012f55  lea     rdx, [rbp+0E0h+var_150]; struct _IMAGE_NT_HEADERS64 *
0x180012f59  mov     rcx, rdi; void *
0x180012f5c  call    ?GenImageNtHeader@@YAPEAU_IMAGE_NT_HEADERS64@@PEAXPEAU1@@Z; GenImageNtHeader(void *,_IMAGE_NT_HEADERS64 *)
0x180012f61  mov     rcx, [rsi+30h]
0x180012f65  mov     rbx, rax
0x180012f68  mov     rdx, [rcx]
0x180012f6b  mov     rax, [rdx+18h]
0x180012f6f  mov     rdx, rdi
0x180012f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f77  test    rbx, rbx
0x180012f7a  jnz     short loc_180012F83
0x180012f7c  mov     eax, 80070482h
0x180012f81  jmp     short loc_180012FE8
0x180012f83  movzx   eax, [rbp+0E0h+var_150.FileHeader.Machine]
0x180012f87  mov     rcx, [rsp+1E0h+var_1A0]
0x180012f8c  mov     [r12], eax
0x180012f90  mov     eax, [rbp+0E0h+var_150.OptionalHeader.SizeOfImage]
0x180012f93  mov     [r13+0], eax
0x180012f97  mov     eax, [rbp+0E0h+var_150.OptionalHeader.CheckSum]
0x180012f9a  mov     [rcx], eax
0x180012f9c  mov     eax, [rbp+0E0h+var_150.FileHeader.TimeDateStamp]
0x180012f9f  mov     rcx, [rsp+1E0h+var_198]
0x180012fa4  mov     [rcx], eax
0x180012fa6  mov     eax, 10Bh
0x180012fab  cmp     [rbp+0E0h+var_150.OptionalHeader.Magic], ax
0x180012faf  jnz     short loc_180012FB5
0x180012fb1  mov     al, 4
0x180012fb3  jmp     short loc_180012FC2
0x180012fb5  mov     eax, 20Bh
0x180012fba  cmp     [rbp+0E0h+var_150.OptionalHeader.Magic], ax
0x180012fbe  jnz     short loc_180012FDF
0x180012fc0  mov     al, 8
0x180012fc2  mov     [r14], al
0x180012fc5  cmp     [rbp+0E0h+var_150.OptionalHeader.NumberOfRvaAndSizes], 9
0x180012fc9  jbe     short loc_180012FD6
0x180012fcb  cmp     [rbp+0E0h+var_150.OptionalHeader.DataDirectory.Size+48h], 0
0x180012fcf  jbe     short loc_180012FD6
0x180012fd1  mov     eax, [rbp+0E0h+var_150.OptionalHeader.DataDirectory.VirtualAddress+48h]
0x180012fd4  jmp     short loc_180012FD8
0x180012fd6  xor     eax, eax
0x180012fd8  mov     [r15], eax
0x180012fdb  xor     eax, eax
0x180012fdd  jmp     short loc_180012FE8
0x180012fdf  mov     byte ptr [r14], 0
0x180012fe3  mov     eax, 0D000007Bh
0x180012fe8  mov     rcx, [rbp+0E0h+var_40]
0x180012fef  xor     rcx, rsp; StackCookie
0x180012ff2  call    __security_check_cookie
0x180012ff7  mov     rbx, [rsp+1E0h+arg_10]
0x180012fff  add     rsp, 1B0h
0x180013006  pop     r15
0x180013008  pop     r14
0x18001300a  pop     r13
0x18001300c  pop     r12
0x18001300e  pop     rdi
0x18001300f  pop     rsi
0x180013010  pop     rbp
0x180013011  retn
```
