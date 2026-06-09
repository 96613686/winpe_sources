# WriteRecordAsText(void *,CLogInfo *,_EVENTLOGRECORD *,ushort,CTextBuffer *,char * *,ulong *)

- ea: `0x18001766c`
- end: `0x180017997`
- name: `?WriteRecordAsText@@YAJPEAXPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@GPEAVCTextBuffer@@PEAPEADPEAK@Z`
- size: `811`
- prototype: `__int64 __fastcall(void *, struct CLogInfo *, struct _EVENTLOGRECORD *, unsigned __int16, wchar_t **, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800172cc`

## callees

- `0x18000d814`
- `0x18001766c`
- `0x180019a28`
- `0x180019ae4`
- `0x180019b68`
- `0x180019be8`
- `0x180019c40`
- `0x18001e714`
- `0x18001e8c0`
- `0x18001e978`
- `0x1800222d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800177cc`
- `msvcrt!swprintf_s` at `0x1800177cc`
- `msvcrt!wcscpy_s` at `0x1800178e7`
- `msvcrt!wcscpy_s` at `0x1800178e7`
- `KERNEL32!WriteFile` at `0x180017943`
- `KERNEL32!WriteFile` at `0x180017943`
- `KERNEL32!GetLastError` at `0x18001794d`
- `KERNEL32!GetLastError` at `0x18001794d`
- `KERNEL32!LocalFree` at `0x180017965`
- `KERNEL32!LocalFree` at `0x180017965`

## pseudocode

```c
__int64 __fastcall WriteRecordAsText(
        void *a1,
        struct CLogInfo *a2,
        struct _EVENTLOGRECORD *a3,
        unsigned __int16 a4,
        wchar_t **a5,
        char **a6,
        unsigned int *a7)
{
  DWORD TimeGenerated; // ecx
  unsigned __int16 *v11; // r12
  signed int appended; // ebx
  struct _EVENTLOGRECORD *v13; // r15
  const unsigned __int16 *TypeStr; // rax
  const unsigned __int16 *DescriptionStr; // rax
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rcx
  char **v19; // rsi
  unsigned int *v20; // r8
  char **v21; // rdx
  signed int LastError; // eax
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int *v26; // [rsp+38h] [rbp-C8h]
  char **v27; // [rsp+40h] [rbp-C0h]
  HANDLE hFile; // [rsp+48h] [rbp-B8h]
  wchar_t Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v27 = a6;
  hFile = a1;
  TimeGenerated = a3->TimeGenerated;
  v11 = 0;
  v26 = a7;
  GetDateStr(TimeGenerated, Buffer, 0x104u);
  appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, Buffer, a4, 1);
  if ( appended >= 0 )
  {
    GetTimeStr(a3->TimeGenerated, Buffer, 0x104u);
    appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, Buffer, a4, 1);
    if ( appended >= 0 )
    {
      v13 = a3 + 1;
      appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, (const unsigned __int16 *)&a3[1], a4, 1);
      if ( appended >= 0 )
      {
        TypeStr = GetTypeStr(a3->EventType);
        appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, TypeStr, a4, 1);
        if ( appended >= 0 )
        {
          GetCategoryStr(a2, a3, Buffer, 0x104u);
          appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, Buffer, a4, 1);
          if ( appended >= 0 )
          {
            swprintf_s(Buffer, 0x104u, L"%u", LOWORD(a3->EventID));
            appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, Buffer, a4, 1);
            if ( appended >= 0 )
            {
              GetUserStr(a3, Buffer, 0x104u, 1);
              appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, Buffer, a4, 1);
              if ( appended >= 0 )
              {
                DescriptionStr = GetDescriptionStr((__int64)a2, a3, 0, 0, 0);
                v11 = (unsigned __int16 *)DescriptionStr;
                if ( DescriptionStr && *DescriptionStr )
                {
                  v16 = -1;
                  do
                    ++v16;
                  while ( *((_WORD *)&v13->Length + v16) );
                  appended = CTextBuffer::AppendDelimited(
                               (CTextBuffer *)a5,
                               (const unsigned __int16 *)&v13->Length + v16 + 1,
                               a4,
                               1);
                  if ( appended < 0 )
                    goto LABEL_25;
                  v17 = v11;
                }
                else
                {
                  v18 = -1;
                  do
                    ++v18;
                  while ( *((_WORD *)&v13->Length + v18) );
                  v17 = (const unsigned __int16 *)&v13->Length + v18 + 1;
                }
                appended = CTextBuffer::AppendDelimited((CTextBuffer *)a5, v17, a4, 0);
                if ( appended >= 0 )
                {
                  appended = CTextBuffer::_ExpandBy((CTextBuffer *)a5, 2u);
                  if ( appended >= 0 )
                  {
                    wcscpy_s(a5[2], *((unsigned int *)a5 + 2) - (a5[2] - *a5), L"\r\n");
                    v19 = v27;
                    v20 = v26;
                    v21 = v27;
                    a5[2] += 2;
                    v24 = 0;
                    appended = CTextBuffer::GetBufferA((CTextBuffer *)a5, v21, v20, &v24);
                    if ( appended >= 0 )
                    {
                      NumberOfBytesWritten = 0;
                      if ( v24 > 1 )
                      {
                        if ( !WriteFile(hFile, *v19, v24 - 1, &NumberOfBytesWritten, 0) )
                        {
                          LastError = GetLastError();
                          appended = LastError;
                          if ( LastError > 0 )
                            appended = (unsigned __int16)LastError | 0x80070000;
                        }
                      }
                      else
                      {
                        appended = 1;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_25:
  LocalFree(v11);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001766c  mov     [rsp-8+arg_18], rbx
0x180017671  push    rbp
0x180017672  push    rsi
0x180017673  push    rdi
0x180017674  push    r12
0x180017676  push    r13
0x180017678  push    r14
0x18001767a  push    r15
0x18001767c  lea     rbp, [rsp-170h]
0x180017684  sub     rsp, 270h
0x18001768b  mov     rax, cs:__security_cookie
0x180017692  xor     rax, rsp
0x180017695  mov     [rbp+1A0h+var_40], rax
0x18001769c  mov     rax, [rbp+1A0h+arg_28]
0x1800176a3  mov     r14, r8
0x1800176a6  mov     rdi, [rbp+1A0h+arg_20]
0x1800176ad  mov     r13, rdx
0x1800176b0  mov     [rsp+2A0h+var_260], rax
0x1800176b5  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x1800176ba  mov     rax, [rbp+1A0h+arg_30]
0x1800176c1  mov     r8d, 104h; unsigned int
0x1800176c7  mov     [rsp+2A0h+hFile], rcx
0x1800176cc  movzx   esi, r9w
0x1800176d0  mov     ecx, [r14+0Ch]; unsigned int
0x1800176d4  xor     r12d, r12d
0x1800176d7  mov     [rsp+2A0h+var_268], rax
0x1800176dc  call    ?GetDateStr@@YAPEAGKPEAGK@Z; GetDateStr(ulong,ushort *,ulong)
0x1800176e1  lea     r15d, [r12+1]
0x1800176e6  movzx   r8d, si; unsigned __int16
0x1800176ea  mov     r9d, r15d; int
0x1800176ed  lea     rdx, [rsp+2A0h+Buffer]; Src
0x1800176f2  mov     rcx, rdi; this
0x1800176f5  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x1800176fa  mov     ebx, eax
0x1800176fc  test    eax, eax
0x1800176fe  js      loc_180017962
0x180017704  mov     ecx, [r14+0Ch]; unsigned int
0x180017708  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001770d  mov     r8d, 104h; unsigned int
0x180017713  call    ?GetTimeStr@@YAPEAGKPEAGK@Z; GetTimeStr(ulong,ushort *,ulong)
0x180017718  mov     r9d, r15d; int
0x18001771b  lea     rdx, [rsp+2A0h+Buffer]; Src
0x180017720  movzx   r8d, si; unsigned __int16
0x180017724  mov     rcx, rdi; this
0x180017727  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x18001772c  mov     ebx, eax
0x18001772e  test    eax, eax
0x180017730  js      loc_180017962
0x180017736  lea     r15, [r14+38h]
0x18001773a  movzx   r8d, si; unsigned __int16
0x18001773e  mov     rdx, r15; Src
0x180017741  lea     r9d, [r12+1]; int
0x180017746  mov     rcx, rdi; this
0x180017749  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x18001774e  mov     ebx, eax
0x180017750  test    eax, eax
0x180017752  js      loc_180017962
0x180017758  movzx   ecx, word ptr [r14+18h]; unsigned __int16
0x18001775d  call    ?GetTypeStr@@YAPEAGG@Z; GetTypeStr(ushort)
0x180017762  mov     rdx, rax; Src
0x180017765  lea     r9d, [r12+1]; int
0x18001776a  movzx   r8d, si; unsigned __int16
0x18001776e  mov     rcx, rdi; this
0x180017771  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x180017776  mov     ebx, eax
0x180017778  test    eax, eax
0x18001777a  js      loc_180017962
0x180017780  mov     r9d, 104h; unsigned int
0x180017786  lea     r8, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001778b  mov     rdx, r14; struct _EVENTLOGRECORD *
0x18001778e  mov     rcx, r13; struct CLogInfo *
0x180017791  call    ?GetCategoryStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAGK@Z; GetCategoryStr(CLogInfo *,_EVENTLOGRECORD *,ushort *,ulong)
0x180017796  lea     r9d, [r12+1]; int
0x18001779b  movzx   r8d, si; unsigned __int16
0x18001779f  lea     rdx, [rsp+2A0h+Buffer]; Src
0x1800177a4  mov     rcx, rdi; this
0x1800177a7  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x1800177ac  mov     ebx, eax
0x1800177ae  test    eax, eax
0x1800177b0  js      loc_180017962
0x1800177b6  movzx   r9d, word ptr [r14+14h]
0x1800177bb  lea     r8, aU_0; "%u"
0x1800177c2  mov     edx, 104h; BufferCount
0x1800177c7  lea     rcx, [rsp+2A0h+Buffer]; Buffer
0x1800177cc  call    cs:__imp_swprintf_s
0x1800177d2  lea     r9d, [r12+1]; int
0x1800177d7  movzx   r8d, si; unsigned __int16
0x1800177db  lea     rdx, [rsp+2A0h+Buffer]; Src
0x1800177e0  mov     rcx, rdi; this
0x1800177e3  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x1800177e8  mov     ebx, eax
0x1800177ea  test    eax, eax
0x1800177ec  js      loc_180017962
0x1800177f2  lea     ebx, [r12+1]
0x1800177f7  mov     r8d, 104h; unsigned int
0x1800177fd  mov     r9d, ebx; int
0x180017800  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180017805  mov     rcx, r14; struct _EVENTLOGRECORD *
0x180017808  call    ?GetUserStr@@YAPEAGPEAU_EVENTLOGRECORD@@PEAGKH@Z; GetUserStr(_EVENTLOGRECORD *,ushort *,ulong,int)
0x18001780d  mov     r9d, ebx; int
0x180017810  lea     rdx, [rsp+2A0h+Buffer]; Src
0x180017815  movzx   r8d, si; unsigned __int16
0x180017819  mov     rcx, rdi; this
0x18001781c  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x180017821  mov     ebx, eax
0x180017823  test    eax, eax
0x180017825  js      loc_180017962
0x18001782b  xor     r9d, r9d
0x18001782e  mov     [rsp+2A0h+lpOverlapped], r12
0x180017833  xor     r8d, r8d
0x180017836  mov     rdx, r14
0x180017839  mov     rcx, r13
0x18001783c  call    ?GetDescriptionStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEAPEAG@Z; GetDescriptionStr(CLogInfo *,_EVENTLOGRECORD *,std::wstring *,int,ushort * *)
0x180017841  xor     r14d, r14d
0x180017844  mov     r12, rax
0x180017847  test    rax, rax
0x18001784a  jz      short loc_180017888
0x18001784c  cmp     [rax], r14w
0x180017850  jz      short loc_180017888
0x180017852  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017856  inc     rcx
0x180017859  cmp     [r15+rcx*2], r14w
0x18001785e  jnz     short loc_180017856
0x180017860  inc     rcx
0x180017863  mov     r9d, 1; int
0x180017869  movzx   r8d, si; unsigned __int16
0x18001786d  lea     rdx, [r15+rcx*2]; Src
0x180017871  mov     rcx, rdi; this
0x180017874  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x180017879  mov     ebx, eax
0x18001787b  test    eax, eax
0x18001787d  js      loc_180017962
0x180017883  mov     rdx, r12
0x180017886  jmp     short loc_18001789D
0x180017888  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001788c  inc     rcx
0x18001788f  cmp     [r15+rcx*2], r14w
0x180017894  jnz     short loc_18001788C
0x180017896  inc     rcx
0x180017899  lea     rdx, [r15+rcx*2]; Src
0x18001789d  xor     r9d, r9d; int
0x1800178a0  movzx   r8d, si; unsigned __int16
0x1800178a4  mov     rcx, rdi; this
0x1800178a7  call    ?AppendDelimited@CTextBuffer@@QEAAJPEBGGH@Z; CTextBuffer::AppendDelimited(ushort const *,ushort,int)
0x1800178ac  mov     ebx, eax
0x1800178ae  test    eax, eax
0x1800178b0  js      loc_180017962
0x1800178b6  mov     edx, 2; unsigned int
0x1800178bb  mov     rcx, rdi; this
0x1800178be  call    ?_ExpandBy@CTextBuffer@@AEAAJK@Z; CTextBuffer::_ExpandBy(ulong)
0x1800178c3  mov     ebx, eax
0x1800178c5  test    eax, eax
0x1800178c7  js      loc_180017962
0x1800178cd  mov     rcx, [rdi+10h]; Destination
0x1800178d1  lea     r8, asc_180028B10; "\r\n"
0x1800178d8  mov     edx, [rdi+8]
0x1800178db  mov     rax, rcx
0x1800178de  sub     rax, [rdi]
0x1800178e1  sar     rax, 1
0x1800178e4  sub     rdx, rax; SizeInWords
0x1800178e7  call    cs:__imp_wcscpy_s
0x1800178ed  mov     rsi, [rsp+2A0h+var_260]
0x1800178f2  lea     r9, [rsp+2A0h+var_270]; unsigned int *
0x1800178f7  mov     r8, [rsp+2A0h+var_268]; unsigned int *
0x1800178fc  mov     rdx, rsi; char **
0x1800178ff  add     qword ptr [rdi+10h], 4
0x180017904  mov     rcx, rdi; this
0x180017907  mov     [rsp+2A0h+var_270], r14d
0x18001790c  call    ?GetBufferA@CTextBuffer@@QEAAJPEAPEADPEAK1@Z; CTextBuffer::GetBufferA(char * *,ulong *,ulong *)
0x180017911  mov     ebx, eax
0x180017913  test    eax, eax
0x180017915  js      short loc_180017962
0x180017917  mov     r8d, [rsp+2A0h+var_270]
0x18001791c  mov     [rsp+2A0h+NumberOfBytesWritten], r14d
0x180017921  cmp     r8d, 1
0x180017925  ja      short loc_18001792E
0x180017927  mov     ebx, 1
0x18001792c  jmp     short loc_180017962
0x18001792e  mov     rdx, [rsi]; lpBuffer
0x180017931  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180017936  mov     rcx, [rsp+2A0h+hFile]; hFile
0x18001793b  dec     r8d; nNumberOfBytesToWrite
0x18001793e  mov     [rsp+2A0h+lpOverlapped], r14; lpOverlapped
0x180017943  call    cs:__imp_WriteFile
0x180017949  test    eax, eax
0x18001794b  jnz     short loc_180017962
0x18001794d  call    cs:__imp_GetLastError
0x180017953  mov     ebx, eax
0x180017955  test    eax, eax
0x180017957  jle     short loc_180017962
0x180017959  movzx   ebx, ax
0x18001795c  or      ebx, 80070000h
0x180017962  mov     rcx, r12; hMem
0x180017965  call    cs:__imp_LocalFree
0x18001796b  mov     eax, ebx
0x18001796d  mov     rcx, [rbp+1A0h+var_40]
0x180017974  xor     rcx, rsp; StackCookie
0x180017977  call    __security_check_cookie
0x18001797c  mov     rbx, [rsp+2A0h+arg_18]
0x180017984  add     rsp, 270h
0x18001798b  pop     r15
0x18001798d  pop     r14
0x18001798f  pop     r13
0x180017991  pop     r12
0x180017993  pop     rdi
0x180017994  pop     rsi
0x180017995  pop     rbp
0x180017996  retn
```
