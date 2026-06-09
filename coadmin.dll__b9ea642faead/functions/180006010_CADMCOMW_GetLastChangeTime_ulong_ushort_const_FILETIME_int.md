# CADMCOMW::GetLastChangeTime(ulong,ushort const *,_FILETIME *,int)

- ea: `0x180006010`
- end: `0x18000611f`
- name: `?GetLastChangeTime@CADMCOMW@@UEAAJKPEBGPEAU_FILETIME@@H@Z`
- size: `271`
- prototype: `int(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, struct _FILETIME *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006010`
- `0x18000716c`
- `0x180010010`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x1800060f0`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800060f0`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetLastChangeTime(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4,
        int a5)
{
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v12; // [rsp+60h] [rbp-10h] BYREF
  FILETIME FileTime; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+A8h] [rbp+38h] BYREF

  v14 = 0;
  FileTime = 0;
  v12 = 0;
  if ( a4 )
  {
    v8 = CADMCOMW::LookupAndAccessCheck(this, a2, &v14, (__int64)a3, 1u, 0, 0, 0, 0, &v12, 0);
    if ( v8 >= 0 )
    {
      v9 = *((_QWORD *)this + 101);
      if ( v9 && v12 == 1 )
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, FILETIME *))(*(_QWORD *)v9 + 136LL))(
                v9,
                v14,
                a3,
                &FileTime);
      else
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, FILETIME *))(**((_QWORD **)this + 4)
                                                                                              + 384LL))(
                *((_QWORD *)this + 4),
                v14,
                a3,
                &FileTime);
      v8 = v10;
      if ( v10 >= 0 )
      {
        if ( a5 )
        {
          if ( !FileTimeToLocalFileTime(&FileTime, a4) )
            return (unsigned int)-2147418113;
        }
        else
        {
          *a4 = FileTime;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006010  mov     [rsp-18h+arg_0], rbx
0x180006015  mov     [rsp-18h+arg_8], rsi
0x18000601a  push    rbp
0x18000601b  push    rdi
0x18000601c  push    r14
0x18000601e  mov     rbp, rsp
0x180006021  sub     rsp, 70h
0x180006025  mov     [rbp+arg_18], 0
0x18000602c  mov     rdi, r9
0x18000602f  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180006037  mov     r14, r8
0x18000603a  mov     [rbp+var_10], 0
0x180006041  mov     rsi, rcx
0x180006044  test    r9, r9
0x180006047  jnz     short loc_180006053
0x180006049  mov     ebx, 80070057h
0x18000604e  jmp     loc_180006108
0x180006053  mov     [rsp+70h+var_20], 0
0x18000605c  lea     rax, [rbp+var_10]
0x180006060  mov     [rsp+70h+var_28], rax
0x180006065  lea     r8, [rbp+arg_18]
0x180006069  mov     [rsp+70h+var_30], 0
0x180006072  mov     r9, r14
0x180006075  mov     [rsp+70h+var_38], 0
0x18000607e  mov     [rsp+70h+var_40], 0
0x180006087  mov     [rsp+70h+var_48], 0
0x18000608f  mov     [rsp+70h+var_50], 1
0x180006097  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x18000609c  mov     ebx, eax
0x18000609e  test    eax, eax
0x1800060a0  js      short loc_180006108
0x1800060a2  mov     rcx, [rsi+328h]
0x1800060a9  test    rcx, rcx
0x1800060ac  jz      short loc_1800060C0
0x1800060ae  cmp     [rbp+var_10], 1
0x1800060b2  jnz     short loc_1800060C0
0x1800060b4  mov     rax, [rcx]
0x1800060b7  mov     rax, [rax+88h]
0x1800060be  jmp     short loc_1800060CE
0x1800060c0  mov     rcx, [rsi+20h]
0x1800060c4  mov     rax, [rcx]
0x1800060c7  mov     rax, [rax+180h]
0x1800060ce  mov     edx, [rbp+arg_18]
0x1800060d1  lea     r9, [rbp+FileTime]
0x1800060d5  mov     r8, r14
0x1800060d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060dd  mov     ebx, eax
0x1800060df  test    eax, eax
0x1800060e1  js      short loc_180006108
0x1800060e3  cmp     [rbp+arg_20], 0
0x1800060e7  jz      short loc_180006101
0x1800060e9  mov     rdx, rdi; lpLocalFileTime
0x1800060ec  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800060f0  call    cs:__imp_FileTimeToLocalFileTime
0x1800060f6  test    eax, eax
0x1800060f8  jnz     short loc_180006108
0x1800060fa  mov     ebx, 8000FFFFh
0x1800060ff  jmp     short loc_180006108
0x180006101  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x180006105  mov     [rdi], rax
0x180006108  lea     r11, [rsp+70h+var_s0]
0x18000610d  mov     eax, ebx
0x18000610f  mov     rbx, [r11+20h]
0x180006113  mov     rsi, [r11+28h]
0x180006117  mov     rsp, r11
0x18000611a  pop     r14
0x18000611c  pop     rdi
0x18000611d  pop     rbp
0x18000611e  retn
```
