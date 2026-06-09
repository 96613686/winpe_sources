# NtWin32LiveSystemProvider::EnumHandles(unsigned __int64 *,ulong *,ulong *,ulong *,ulong *,ushort *,ulong,ushort *,ulong)

- ea: `0x180023dc0`
- end: `0x180024088`
- name: `?EnumHandles@NtWin32LiveSystemProvider@@UEAAJPEA_KPEAK111PEAGK2K@Z`
- size: `712`
- prototype: `__int64 __usercall@<rax>(NtWin32LiveSystemProvider *__hidden this@<rcx>, unsigned __int64 *@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned int *, unsigned int *, LPCWSTR lpString1, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003424`
- `0x180023398`
- `0x180023dc0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023f9d`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002404b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002404b`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::EnumHandles(
        NtWin32LiveSystemProvider *this,
        unsigned __int64 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        WCHAR *lpString1,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned int a10)
{
  unsigned __int64 *v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  int v18; // eax
  unsigned int *v19; // rcx
  __int64 result; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned __int64 v23; // rbx
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned __int64 v26; // rbx
  unsigned int *v27; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v29; // [rsp+38h] [rbp-C8h]
  unsigned int *v30; // [rsp+40h] [rbp-C0h]
  __int128 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h]
  __int128 v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  unsigned __int16 v35; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+88h] [rbp-78h]

  v29 = a6;
  v30 = a5;
  v34 = 0;
  hObject = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  while ( 1 )
  {
    v14 = (unsigned __int64 *)*((_QWORD *)this + 136);
    if ( !v14 )
      break;
    v15 = *((unsigned int *)this + 274);
    if ( v15 >= *v14 )
      goto LABEL_27;
    v16 = v14[5 * v15 + 2];
    *((_DWORD *)this + 274) = v15 + 1;
LABEL_7:
    *((_DWORD *)this + 271) = v16;
    v18 = NtWin32LiveSystemProvider::DupSame(this, v16, &hObject);
    if ( !v18 )
    {
      if ( (*((int (__fastcall **)(HANDLE, _QWORD, __int128 *, __int64, _QWORD))this + 108))(hObject, 0, &v31, 56, 0) < 0 )
      {
        v31 = 0;
        v34 = 0;
        v32 = 0;
        v33 = 0;
      }
      if ( (*((int (__fastcall **)(HANDLE, __int64, unsigned __int16 *, __int64, _QWORD))this + 108))(
             hObject,
             2,
             &v35,
             1024,
             0) < 0 )
        memset_0(&v35, 0, 0x400u);
      v21 = a8 - 1;
      v22 = 2 * v21;
      if ( v35 <= (unsigned __int64)(2 * v21) )
        v22 = v35;
      v23 = v22;
      memcpy_0(lpString1, Src, v22);
      lpString1[v23 >> 1] = 0;
      if ( lstrcmpiW(lpString1, L"File")
        && (*((int (__fastcall **)(HANDLE, __int64, unsigned __int16 *, __int64, _QWORD))this + 108))(
             hObject,
             1,
             &v35,
             1024,
             0) >= 0
        && Src )
      {
        v24 = a10 - 1;
        v25 = 2 * v24;
        if ( v35 <= (unsigned __int64)(2 * v24) )
          v25 = v35;
        v26 = v25;
        memcpy_0(a9, Src, v25);
        a9[v26 >> 1] = 0;
      }
      else
      {
        *a9 = 0;
      }
      v27 = v30;
      *a2 = *((unsigned int *)this + 271);
      *a3 = v31;
      *a4 = DWORD1(v31);
      *v27 = DWORD2(v31);
      *v29 = HIDWORD(v31);
      CloseHandle(hObject);
      return 0;
    }
    if ( v18 == -2147024846 && *((_DWORD *)this + 17) >= 0x1770u )
    {
      v19 = v29;
      *a2 = *((unsigned int *)this + 271);
      *lpString1 = 0;
      *a9 = 0;
      *a3 = 0;
      *a4 = 0;
      *a5 = 0;
      *v19 = 0;
      return 0;
    }
  }
  v17 = *((_DWORD *)this + 271);
  if ( v17 < 0x4000000 )
  {
    v16 = v17 + 4;
    goto LABEL_7;
  }
  *((_DWORD *)this + 271) = 0;
LABEL_27:
  result = 2415919130LL;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180023dc0  push    rbp
0x180023dc2  push    rbx
0x180023dc3  push    rsi
0x180023dc4  push    rdi
0x180023dc5  push    r12
0x180023dc7  push    r13
0x180023dc9  push    r14
0x180023dcb  push    r15
0x180023dcd  lea     rbp, [rsp-398h]
0x180023dd5  sub     rsp, 498h
0x180023ddc  mov     rax, cs:__security_cookie
0x180023de3  xor     rax, rsp
0x180023de6  mov     [rbp+3D0h+var_50], rax
0x180023ded  mov     rax, [rbp+3D0h+arg_28]
0x180023df4  xorps   xmm0, xmm0
0x180023df7  mov     rbx, [rbp+3D0h+arg_20]
0x180023dfe  mov     r13, r9
0x180023e01  mov     r15, [rbp+3D0h+lpString1]
0x180023e08  mov     r12, r8
0x180023e0b  mov     r14, [rbp+3D0h+arg_40]
0x180023e12  mov     rsi, rdx
0x180023e15  mov     [rsp+4D0h+var_498], rax
0x180023e1a  mov     rdi, rcx
0x180023e1d  xor     eax, eax
0x180023e1f  mov     [rsp+4D0h+var_490], rbx
0x180023e24  xor     r9d, r9d
0x180023e27  mov     [rsp+4D0h+var_458], rax
0x180023e2c  mov     [rsp+4D0h+hObject], r9
0x180023e31  movups  [rsp+4D0h+var_488], xmm0
0x180023e36  movups  [rsp+4D0h+var_478], xmm0
0x180023e3b  movups  [rsp+4D0h+var_468], xmm0
0x180023e40  mov     rdx, [rdi+440h]
0x180023e47  test    rdx, rdx
0x180023e4a  jz      short loc_180023E6F
0x180023e4c  mov     ecx, [rdi+448h]
0x180023e52  cmp     rcx, [rdx]
0x180023e55  jnb     loc_18002405D
0x180023e5b  lea     rax, [rcx+rcx*4]
0x180023e5f  mov     r8d, [rdx+rax*8+10h]
0x180023e64  lea     eax, [rcx+1]
0x180023e67  mov     [rdi+448h], eax
0x180023e6d  jmp     short loc_180023E87
0x180023e6f  mov     r8d, [rdi+43Ch]
0x180023e76  cmp     r8d, 4000000h
0x180023e7d  jnb     loc_180024056
0x180023e83  add     r8d, 4
0x180023e87  mov     [rdi+43Ch], r8d
0x180023e8e  mov     rcx, rdi; this
0x180023e91  mov     edx, r8d; unsigned __int64
0x180023e94  lea     r8, [rsp+4D0h+hObject]; void **
0x180023e99  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023e9e  xor     r9d, r9d
0x180023ea1  test    eax, eax
0x180023ea3  jz      short loc_180023EE0
0x180023ea5  cmp     eax, 80070032h
0x180023eaa  jnz     short loc_180023E40
0x180023eac  cmp     dword ptr [rdi+44h], 1770h
0x180023eb3  jb      short loc_180023E40
0x180023eb5  mov     eax, [rdi+43Ch]
0x180023ebb  mov     rcx, [rsp+4D0h+var_498]
0x180023ec0  mov     [rsi], rax
0x180023ec3  mov     [r15], r9w
0x180023ec7  mov     [r14], r9w
0x180023ecb  mov     [r12], r9d
0x180023ecf  mov     [r13+0], r9d
0x180023ed3  mov     [rbx], r9d
0x180023ed6  mov     [rcx], r9d
0x180023ed9  xor     eax, eax
0x180023edb  jmp     loc_180024065
0x180023ee0  mov     rcx, [rsp+4D0h+hObject]
0x180023ee5  lea     r8, [rsp+4D0h+var_488]
0x180023eea  mov     rax, [rdi+360h]
0x180023ef1  xor     edx, edx
0x180023ef3  mov     [rsp+4D0h+var_4B0], r9
0x180023ef8  mov     r9d, 38h ; '8'
0x180023efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f03  test    eax, eax
0x180023f05  jns     short loc_180023F20
0x180023f07  xorps   xmm0, xmm0
0x180023f0a  xor     eax, eax
0x180023f0c  movups  [rsp+4D0h+var_488], xmm0
0x180023f11  mov     [rsp+4D0h+var_458], rax
0x180023f16  movups  [rsp+4D0h+var_478], xmm0
0x180023f1b  movups  [rsp+4D0h+var_468], xmm0
0x180023f20  mov     rcx, [rsp+4D0h+hObject]
0x180023f25  lea     r8, [rbp+3D0h+var_450]
0x180023f29  mov     rax, [rdi+360h]
0x180023f30  mov     ebx, 400h
0x180023f35  mov     r9d, ebx
0x180023f38  mov     [rsp+4D0h+var_4B0], 0
0x180023f41  mov     edx, 2
0x180023f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f4b  test    eax, eax
0x180023f4d  jns     short loc_180023F5D
0x180023f4f  mov     r8d, ebx; Size
0x180023f52  lea     rcx, [rbp+3D0h+var_450]; void *
0x180023f56  xor     edx, edx; Val
0x180023f58  call    memset_0
0x180023f5d  movzx   r8d, [rbp+3D0h+var_450]
0x180023f62  mov     rcx, r15; void *
0x180023f65  mov     eax, [rbp+3D0h+arg_38]
0x180023f6b  dec     eax
0x180023f6d  mov     edx, eax
0x180023f6f  add     eax, eax
0x180023f71  add     rdx, rdx
0x180023f74  cmp     r8, rdx
0x180023f77  mov     rdx, [rbp+3D0h+Src]; Src
0x180023f7b  cmovbe  eax, r8d
0x180023f7f  mov     r8d, eax; Size
0x180023f82  mov     ebx, eax
0x180023f84  call    memcpy_0
0x180023f89  xor     eax, eax
0x180023f8b  shr     rbx, 1
0x180023f8e  lea     rdx, aFile; "File"
0x180023f95  mov     rcx, r15; lpString1
0x180023f98  mov     [r15+rbx*2], ax
0x180023f9d  call    cs:__imp_lstrcmpiW
0x180023fa3  test    eax, eax
0x180023fa5  jz      short loc_180024011
0x180023fa7  mov     rcx, [rsp+4D0h+hObject]
0x180023fac  lea     r8, [rbp+3D0h+var_450]
0x180023fb0  mov     rax, [rdi+360h]
0x180023fb7  mov     r9d, 400h
0x180023fbd  mov     edx, 1
0x180023fc2  mov     [rsp+4D0h+var_4B0], 0
0x180023fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fd0  test    eax, eax
0x180023fd2  js      short loc_180024011
0x180023fd4  mov     rdx, [rbp+3D0h+Src]; Src
0x180023fd8  test    rdx, rdx
0x180023fdb  jz      short loc_180024011
0x180023fdd  movzx   r8d, [rbp+3D0h+var_450]
0x180023fe2  mov     eax, [rbp+3D0h+arg_48]
0x180023fe8  dec     eax
0x180023fea  mov     ecx, eax
0x180023fec  add     eax, eax
0x180023fee  add     rcx, rcx
0x180023ff1  cmp     r8, rcx
0x180023ff4  mov     rcx, r14; void *
0x180023ff7  cmovbe  eax, r8d
0x180023ffb  mov     r8d, eax; Size
0x180023ffe  mov     ebx, eax
0x180024000  call    memcpy_0
0x180024005  shr     rbx, 1
0x180024008  xor     eax, eax
0x18002400a  mov     [r14+rbx*2], ax
0x18002400f  jmp     short loc_180024017
0x180024011  xor     eax, eax
0x180024013  mov     [r14], ax
0x180024017  mov     eax, [rdi+43Ch]
0x18002401d  mov     rcx, [rsp+4D0h+var_490]
0x180024022  mov     [rsi], rax
0x180024025  mov     eax, dword ptr [rsp+4D0h+var_488]
0x180024029  mov     [r12], eax
0x18002402d  mov     eax, dword ptr [rsp+4D0h+var_488+4]
0x180024031  mov     [r13+0], eax
0x180024035  mov     eax, dword ptr [rsp+4D0h+var_488+8]
0x180024039  mov     [rcx], eax
0x18002403b  mov     rcx, [rsp+4D0h+var_498]
0x180024040  mov     eax, dword ptr [rsp+4D0h+var_488+0Ch]
0x180024044  mov     [rcx], eax
0x180024046  mov     rcx, [rsp+4D0h+hObject]; hObject
0x18002404b  call    cs:__imp_CloseHandle
0x180024051  jmp     loc_180023ED9
0x180024056  mov     [rdi+43Ch], r9d
0x18002405d  mov     eax, 9000001Ah
0x180024062  mov     [rsi], r9
0x180024065  mov     rcx, [rbp+3D0h+var_50]
0x18002406c  xor     rcx, rsp; StackCookie
0x18002406f  call    __security_check_cookie
0x180024074  add     rsp, 498h
0x18002407b  pop     r15
0x18002407d  pop     r14
0x18002407f  pop     r13
0x180024081  pop     r12
0x180024083  pop     rdi
0x180024084  pop     rsi
0x180024085  pop     rbx
0x180024086  pop     rbp
0x180024087  retn
```
