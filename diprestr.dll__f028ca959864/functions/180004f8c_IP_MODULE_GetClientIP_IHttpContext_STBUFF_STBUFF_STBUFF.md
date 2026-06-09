# IP_MODULE::GetClientIP(IHttpContext *,STBUFF *,STBUFF *,STBUFF *)

- ea: `0x180004f8c`
- end: `0x180005162`
- name: `?GetClientIP@IP_MODULE@@CAJPEAVIHttpContext@@PEAVSTBUFF@@11@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct STBUFF *, struct STBUFF *, struct STBUFF *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800047a4`

## callees

- `0x180001948`
- `0x180001a2c`
- `0x180001af4`
- `0x180001fa4`
- `0x180004f8c`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005140`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005140`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetClientIP(
        struct IHttpContext *a1,
        struct STBUFF *a2,
        struct STBUFF *a3,
        struct STBUFF *a4)
{
  int v8; // edx
  __int64 v9; // rax
  int appended; // ebx
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  void *v16; // [rsp+38h] [rbp-C8h] BYREF
  void **v17; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v18; // [rsp+48h] [rbp-B8h]
  unsigned int v19; // [rsp+50h] [rbp-B0h]
  unsigned int v20; // [rsp+54h] [rbp-ACh]
  char v21; // [rsp+5Ch] [rbp-A4h] BYREF
  void **v22; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h]
  unsigned int v24; // [rsp+B0h] [rbp-50h]
  int v25; // [rsp+B4h] [rbp-4Ch]
  _BYTE v26[68]; // [rsp+BCh] [rbp-44h] BYREF

  STBUFF::STBUFF((STBUFF *)&v17, (int)a2);
  STBUFF::STBUFF((STBUFF *)&v22, v8);
  v9 = *(_QWORD *)a1;
  v16 = 0;
  v15 = 0;
  appended = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, void **, unsigned int *))(v9 + 120))(
               a1,
               "REMOTE_ADDR",
               &v16,
               &v15);
  if ( appended >= 0 )
  {
    LODWORD(v11) = v15;
    if ( v15 > v20 )
    {
      appended = STBUFF::Resize((STBUFF *)&v17, v15);
      if ( appended < 0 )
        goto LABEL_17;
      LODWORD(v11) = v15;
    }
    if ( (_DWORD)v11 == -1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *((_BYTE *)v16 + v11) );
    }
    appended = STBUFF::AppendData((STBUFF *)&v17, v16, v11, 0);
    if ( appended >= 0 )
    {
      *((_BYTE *)v18 + v19) = 0;
      *((_BYTE *)v18 + v19 + 1) = 0;
      appended = IpToSockAddr((char *)v18, (struct STBUFF *)&v22);
      if ( appended >= 0 )
      {
        v12 = 8;
        v13 = 16;
        if ( *(_WORD *)hMem != 23 )
        {
          v12 = 4;
          v13 = 4;
        }
        appended = STBUFF::AppendData(a2, (char *)hMem + v12, v13, 0);
        if ( appended >= 0 )
        {
          if ( !a3 || (appended = STBUFF::AppendData(a3, v18, v19, 0), appended >= 0) )
          {
            if ( a4 )
              appended = STBUFF::AppendData(a4, hMem, v24, 0);
          }
        }
      }
    }
  }
LABEL_17:
  v22 = &STBUFF::`vftable';
  if ( hMem != v26 )
  {
    LocalFree(hMem);
    v25 = 64;
    hMem = v26;
  }
  v24 = 0;
  v17 = &STBUFF::`vftable';
  if ( v18 != &v21 )
    LocalFree(v18);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180004f8c  push    rbp
0x180004f8e  push    rbx
0x180004f8f  push    rsi
0x180004f90  push    rdi
0x180004f91  push    r14
0x180004f93  lea     rbp, [rsp-10h]
0x180004f98  sub     rsp, 110h
0x180004f9f  mov     rax, cs:__security_cookie
0x180004fa6  xor     rax, rsp
0x180004fa9  mov     [rbp+30h+var_30], rax
0x180004fad  mov     rbx, rcx
0x180004fb0  mov     rdi, r9
0x180004fb3  lea     rcx, [rsp+130h+var_F0]; this
0x180004fb8  mov     rsi, r8
0x180004fbb  mov     r14, rdx
0x180004fbe  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180004fc3  lea     rcx, [rbp+30h+var_90]; this
0x180004fc7  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180004fcc  mov     rax, [rbx]
0x180004fcf  lea     r9, [rsp+130h+var_100]
0x180004fd4  lea     r8, [rsp+130h+var_F8]
0x180004fd9  mov     [rsp+130h+var_F8], 0
0x180004fe2  lea     rdx, aRemoteAddr; "REMOTE_ADDR"
0x180004fe9  mov     [rsp+130h+var_100], 0
0x180004ff1  mov     rcx, rbx
0x180004ff4  mov     rax, [rax+78h]
0x180004ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffd  mov     ebx, eax
0x180004fff  test    eax, eax
0x180005001  js      loc_1800050F8
0x180005007  mov     r8d, [rsp+130h+var_100]
0x18000500c  cmp     r8d, [rsp+130h+var_DC]
0x180005011  jbe     short loc_18000502F
0x180005013  mov     edx, r8d; unsigned int
0x180005016  lea     rcx, [rsp+130h+var_F0]; this
0x18000501b  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180005020  mov     ebx, eax
0x180005022  test    eax, eax
0x180005024  js      loc_1800050F8
0x18000502a  mov     r8d, [rsp+130h+var_100]
0x18000502f  mov     rdx, [rsp+130h+var_F8]; void *
0x180005034  cmp     r8d, 0FFFFFFFFh
0x180005038  jnz     short loc_180005048
0x18000503a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000503e  inc     r8; unsigned int
0x180005041  cmp     byte ptr [rdx+r8], 0
0x180005046  jnz     short loc_18000503E
0x180005048  xor     r9d, r9d; unsigned int
0x18000504b  lea     rcx, [rsp+130h+var_F0]; this
0x180005050  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005055  mov     ebx, eax
0x180005057  test    eax, eax
0x180005059  js      loc_1800050F8
0x18000505f  mov     ecx, [rsp+130h+var_E0]
0x180005063  lea     rdx, [rbp+30h+var_90]; this
0x180005067  mov     rax, [rsp+130h+var_E8]
0x18000506c  mov     byte ptr [rcx+rax], 0
0x180005070  mov     ecx, [rsp+130h+var_E0]
0x180005074  mov     rax, [rsp+130h+var_E8]
0x180005079  inc     ecx
0x18000507b  mov     byte ptr [rcx+rax], 0
0x18000507f  mov     rcx, [rsp+130h+var_E8]; char *
0x180005084  call    ?IpToSockAddr@@YAJPEADPEAVSTBUFF@@@Z; IpToSockAddr(char *,STBUFF *)
0x180005089  mov     ebx, eax
0x18000508b  test    eax, eax
0x18000508d  js      short loc_1800050F8
0x18000508f  mov     rax, [rbp+30h+hMem]
0x180005093  mov     ecx, 4
0x180005098  cmp     word ptr [rax], 17h
0x18000509c  lea     edx, [rcx+4]
0x18000509f  lea     r8d, [rcx+0Ch]
0x1800050a3  cmovnz  edx, ecx
0x1800050a6  cmovnz  r8d, ecx; unsigned int
0x1800050aa  add     rdx, rax; void *
0x1800050ad  xor     r9d, r9d; unsigned int
0x1800050b0  mov     rcx, r14; this
0x1800050b3  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x1800050b8  mov     ebx, eax
0x1800050ba  test    eax, eax
0x1800050bc  js      short loc_1800050F8
0x1800050be  test    rsi, rsi
0x1800050c1  jz      short loc_1800050DE
0x1800050c3  mov     r8d, [rsp+130h+var_E0]; unsigned int
0x1800050c8  xor     r9d, r9d; unsigned int
0x1800050cb  mov     rdx, [rsp+130h+var_E8]; void *
0x1800050d0  mov     rcx, rsi; this
0x1800050d3  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x1800050d8  mov     ebx, eax
0x1800050da  test    eax, eax
0x1800050dc  js      short loc_1800050F8
0x1800050de  test    rdi, rdi
0x1800050e1  jz      short loc_1800050F8
0x1800050e3  mov     r8d, [rbp+30h+var_80]; unsigned int
0x1800050e7  xor     r9d, r9d; unsigned int
0x1800050ea  mov     rdx, [rbp+30h+hMem]; void *
0x1800050ee  mov     rcx, rdi; this
0x1800050f1  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x1800050f6  mov     ebx, eax
0x1800050f8  mov     rcx, [rbp+30h+hMem]; hMem
0x1800050fc  lea     rax, [rbp+30h+var_74]
0x180005100  lea     rdi, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180005107  mov     [rbp+30h+var_90], rdi
0x18000510b  cmp     rcx, rax
0x18000510e  jz      short loc_180005125
0x180005110  call    cs:__imp_LocalFree
0x180005116  lea     rax, [rbp+30h+var_74]
0x18000511a  mov     [rbp+30h+var_7C], 40h ; '@'
0x180005121  mov     [rbp+30h+hMem], rax
0x180005125  mov     rcx, [rsp+130h+var_E8]; hMem
0x18000512a  lea     rax, [rsp+130h+var_D4]
0x18000512f  mov     [rbp+30h+var_80], 0
0x180005136  mov     [rsp+130h+var_F0], rdi
0x18000513b  cmp     rcx, rax
0x18000513e  jz      short loc_180005146
0x180005140  call    cs:__imp_LocalFree
0x180005146  mov     eax, ebx
0x180005148  mov     rcx, [rbp+30h+var_30]
0x18000514c  xor     rcx, rsp; StackCookie
0x18000514f  call    __security_check_cookie
0x180005154  add     rsp, 110h
0x18000515b  pop     r14
0x18000515d  pop     rdi
0x18000515e  pop     rsi
0x18000515f  pop     rbx
0x180005160  pop     rbp
0x180005161  retn
```
