# CscDriverReplaceSid

- ea: `0x18006fd8c`
- end: `0x18006ff18`
- name: `CscDriverReplaceSid`
- size: `396`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180061ff0`

## callees

- `0x180007280`
- `0x180007a00`
- `0x18000b580`
- `0x18000b8b0`
- `0x180039fb4`
- `0x18006fd8c`
- `0x180087608`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18006fdc7`
- `ntdll!RtlValidSid` at `0x18006fdd8`
- `ntdll!RtlValidSid` at `0x18006fdc7`
- `ntdll!RtlValidSid` at `0x18006fdd8`
- `ntdll!RtlLengthSid` at `0x18006fe02`
- `ntdll!RtlLengthSid` at `0x18006fe28`
- `ntdll!RtlLengthSid` at `0x18006fe02`
- `ntdll!RtlLengthSid` at `0x18006fe28`
- `ntdll!NtClose` at `0x18006feeb`
- `ntdll!NtClose` at `0x18006feeb`

## pseudocode

```c
__int64 __fastcall CscDriverReplaceSid(void *Src, void *a2)
{
  _DWORD *v2; // rdi
  int v5; // ebx
  ULONG v6; // eax
  size_t v7; // r13
  ULONG v8; // r15d
  unsigned int v9; // ebx
  ULONG v10; // eax
  size_t v11; // r12
  ULONG v12; // r14d
  _DWORD *v13; // rax
  __int64 v14; // rdx
  int v16; // [rsp+80h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+18h] BYREF

  v2 = 0;
  v16 = 0;
  Handle = 0;
  if ( Src && a2 && RtlValidSid(Src) && RtlValidSid(a2) )
  {
    v5 = CscDriverpOpenControl(&Handle);
    if ( v5 >= 0 )
    {
      v6 = RtlLengthSid(Src);
      v7 = v6;
      v8 = v6 + 3;
      v9 = ((v6 + 3) & 0xFFFFFFFC) + 8;
      if ( ((v6 + 3) & 0xFFFFFFFC) >= 0xFFFFFFF8 || (v10 = RtlLengthSid(a2), v11 = v10, v12 = v9 + v10, v9 + v10 < v9) )
      {
        v5 = -1073741675;
      }
      else
      {
        v13 = CscDriverpAllocate(v12);
        v2 = v13;
        if ( v13 )
        {
          *v13 = 8;
          v13[1] = 51;
          memset_0(v13 + 2, 0, v12 - 8LL);
          memcpy_0(v2 + 2, Src, v7);
          memcpy_0((char *)v2 + (v8 & 0xFFFFFFFC) + 8, a2, v11);
          v5 = CscDriverpFsControlEx(Handle, v14, &v16, v2, v12, 0, 0);
        }
        else
        {
          v5 = -1073741670;
        }
      }
    }
  }
  else
  {
    v5 = -1073741811;
  }
  if ( Handle )
    NtClose(Handle);
  if ( v2 )
    CscDriverpFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006fd8c  mov     rax, rsp
0x18006fd8f  mov     [rax+10h], rbx
0x18006fd93  push    rbp
0x18006fd94  push    rsi
0x18006fd95  push    rdi
0x18006fd96  push    r12
0x18006fd98  push    r13
0x18006fd9a  push    r14
0x18006fd9c  push    r15
0x18006fd9e  sub     rsp, 40h
0x18006fda2  xor     edi, edi
0x18006fda4  mov     dword ptr [rax+8], 0
0x18006fdab  mov     [rax+18h], rdi
0x18006fdaf  mov     rsi, rdx
0x18006fdb2  mov     rbp, rcx
0x18006fdb5  test    rcx, rcx
0x18006fdb8  jz      loc_18006FED9
0x18006fdbe  test    rdx, rdx
0x18006fdc1  jz      loc_18006FED9
0x18006fdc7  call    cs:__imp_RtlValidSid
0x18006fdcd  test    al, al
0x18006fdcf  jz      loc_18006FED9
0x18006fdd5  mov     rcx, rsi; Sid
0x18006fdd8  call    cs:__imp_RtlValidSid
0x18006fdde  test    al, al
0x18006fde0  jz      loc_18006FED9
0x18006fde6  xor     edx, edx
0x18006fde8  lea     rcx, [rsp+78h+Handle]; FileHandle
0x18006fdf0  call    CscDriverpOpenControl
0x18006fdf5  mov     ebx, eax
0x18006fdf7  test    eax, eax
0x18006fdf9  js      loc_18006FEDE
0x18006fdff  mov     rcx, rbp; Sid
0x18006fe02  call    cs:__imp_RtlLengthSid
0x18006fe08  mov     r13d, eax
0x18006fe0b  mov     eax, 0FFFFFFFCh
0x18006fe10  lea     r15d, [r13+3]
0x18006fe14  mov     ebx, r15d
0x18006fe17  and     ebx, eax
0x18006fe19  add     ebx, 8
0x18006fe1c  cmp     ebx, 8
0x18006fe1f  jb      loc_18006FED2
0x18006fe25  mov     rcx, rsi; Sid
0x18006fe28  call    cs:__imp_RtlLengthSid
0x18006fe2e  mov     r12d, eax
0x18006fe31  lea     r14d, [rbx+r12]
0x18006fe35  cmp     r14d, ebx
0x18006fe38  jb      loc_18006FED2
0x18006fe3e  mov     ecx, r14d; uBytes
0x18006fe41  call    CscDriverpAllocate
0x18006fe46  mov     rdi, rax
0x18006fe49  test    rax, rax
0x18006fe4c  jnz     short loc_18006FE58
0x18006fe4e  mov     ebx, 0C000009Ah
0x18006fe53  jmp     loc_18006FEDE
0x18006fe58  mov     r8d, r14d
0x18006fe5b  lea     rcx, [rax+8]; void *
0x18006fe5f  sub     r8, 8; Size
0x18006fe63  mov     dword ptr [rax], 8
0x18006fe69  xor     edx, edx; Val
0x18006fe6b  mov     dword ptr [rax+4], 33h ; '3'
0x18006fe72  call    memset_0
0x18006fe77  mov     r8, r13; Size
0x18006fe7a  lea     rcx, [rdi+8]; void *
0x18006fe7e  mov     rdx, rbp; Src
0x18006fe81  call    memcpy_0
0x18006fe86  mov     ecx, 0FFFFFFFCh
0x18006fe8b  mov     r8, r12; Size
0x18006fe8e  and     rcx, r15
0x18006fe91  mov     rdx, rsi; Src
0x18006fe94  add     rcx, 8
0x18006fe98  add     rcx, rdi; void *
0x18006fe9b  call    memcpy_0
0x18006fea0  mov     rcx, [rsp+78h+Handle]; FileHandle
0x18006fea8  lea     r8, [rsp+78h+arg_0]
0x18006feb0  mov     [rsp+78h+var_48], 0; ULONG
0x18006feb8  mov     r9, rdi
0x18006febb  mov     [rsp+78h+var_50], 0; PVOID
0x18006fec4  mov     [rsp+78h+var_58], r14d; ULONG
0x18006fec9  call    CscDriverpFsControlEx
0x18006fece  mov     ebx, eax
0x18006fed0  jmp     short loc_18006FEDE
0x18006fed2  mov     ebx, 0C0000095h
0x18006fed7  jmp     short loc_18006FEDE
0x18006fed9  mov     ebx, 0C000000Dh
0x18006fede  mov     rcx, [rsp+78h+Handle]; Handle
0x18006fee6  test    rcx, rcx
0x18006fee9  jz      short loc_18006FEF1
0x18006feeb  call    cs:__imp_NtClose
0x18006fef1  test    rdi, rdi
0x18006fef4  jz      short loc_18006FEFE
0x18006fef6  mov     rcx, rdi
0x18006fef9  call    CscDriverpFree
0x18006fefe  mov     eax, ebx
0x18006ff00  mov     rbx, [rsp+78h+arg_8]
0x18006ff08  add     rsp, 40h
0x18006ff0c  pop     r15
0x18006ff0e  pop     r14
0x18006ff10  pop     r13
0x18006ff12  pop     r12
0x18006ff14  pop     rdi
0x18006ff15  pop     rsi
0x18006ff16  pop     rbp
0x18006ff17  retn
```
