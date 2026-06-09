# cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::Coalesce(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::LibrarySafety>,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)>,std::function<cxl::Exception (std::list<cxl::Exception,std::allocator<cxl::Exception>> &)>,std::function<void (void *)>,std::promise<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::BoxedValueAndException>,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::future<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::BoxedValueAndException>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::future<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation,std::default_delete<AutoImpersonation>>,ClusterHandleConnector>::BoxedValueAndException>>>> &,unsigned __int64)

- ea: `0x1800213c0`
- end: `0x180021c3e`
- name: `?Coalesce@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@CAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLibrarySafety@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@4@V?$function@$$A6AXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4@V?$function@$$A6A?AVException@cxl@@AEAV?$list@VException@cxl@@V?$allocator@VException@cxl@@@std@@@std@@@Z@4@V?$function@$$A6AXPEAX@Z@4@V?$promise@UBoxedValueAndException@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@4@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$future@UBoxedValueAndException@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$future@UBoxedValueAndException@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@2@@std@@@2@@4@_K@Z`
- size: `2174`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: ``

## callers

- `0x180025b40`

## callees

- `0x180002f50`
- `0x18000335c`
- `0x180014090`
- `0x1800142d8`
- `0x1800144a0`
- `0x180019030`
- `0x18001adcc`
- `0x18001b77c`
- `0x18001bd38`
- `0x18001ca34`
- `0x18001cc2c`
- `0x18001d040`
- `0x18001d080`
- `0x18001d284`
- `0x18001e148`
- `0x18001e8e8`
- `0x18001e954`
- `0x18001ecc0`
- `0x18001efa8`
- `0x18001f03c`
- `0x18001f320`
- `0x1800213c0`
- `0x18002696c`
- `0x18002720c`
- `0x180027f00`
- `0x18002927c`
- `0x1800292e4`
- `0x180029578`
- `0x180029d28`
- `0x18002a5ac`
- `0x18002a730`
- `0x180091a0c`
- `0x1800b5010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1800217fa`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x18002186e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180021a8a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180021a8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002181d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800218bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002181d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800218bb`

## string_xrefs

- `0x1800219c7`: ` Launching Cleanup threads for remaining Workers`

## pseudocode

```c

```
